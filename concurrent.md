# server
```C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <arpa/inet.h>

#define PORT 8080
#define BUFFER_SIZE 1024

int main() {
    int server_fd, new_socket;
    struct sockaddr_in address;
    int addrlen = sizeof(address);
    char buffer[BUFFER_SIZE] = {0};
    char response[BUFFER_SIZE] = {0};
    pid_t pid;

    // Creating socket file descriptor
    if ((server_fd = socket(AF_INET, SOCK_STREAM, 0)) == 0) {
        perror("Socket creation failed");
        exit(EXIT_FAILURE);
    }

    address.sin_family = AF_INET;
    address.sin_addr.s_addr = INADDR_ANY;
    address.sin_port = htons(PORT);

    // Binding the socket
    if (bind(server_fd, (struct sockaddr*)&address, sizeof(address)) < 0) {
        perror("Bind failed");
        close(server_fd);
        exit(EXIT_FAILURE);
    }

    // Start listening for connections
    if (listen(server_fd, 3) < 0) {
        perror("Listen failed");
        close(server_fd);
        exit(EXIT_FAILURE);
    }

    printf("Server listening on port %d\n", PORT);

    // Accepting and handling multiple connections using fork
    while (1) {
        if ((new_socket = accept(server_fd, (struct sockaddr*)&address, (socklen_t*)&addrlen)) < 0) {
            perror("Accept failed");
            close(server_fd);
            exit(EXIT_FAILURE);
        }

        // Fork to handle new client
        if ((pid = fork()) == 0) { // Child process
            close(server_fd); // Close the listening socket in the child process

            while (1) {
                memset(buffer, 0, BUFFER_SIZE);
                int bytes_read = read(new_socket, buffer, BUFFER_SIZE);
                if (bytes_read <= 0) {
                    perror("Read failed or client disconnected");
                    break;
                }

                printf("Client: %s\n", buffer);

                // Exit condition
                if (strcmp(buffer, "exit") == 0) {
                    printf("Server exiting client connection...\n");
                    break;
                }

                // Prepare and send response
                printf("Server: ");
                fgets(response, BUFFER_SIZE, stdin);
                response[strcspn(response, "\n")] = '\0'; // Remove newline character
                send(new_socket, response, strlen(response), 0);
            }
            close(new_socket); // Close the socket for the client in the child process
            exit(0); // Exit child process
        } else {
            close(new_socket); // Close client socket in the parent process
        }
    }

    close(server_fd);
    return 0;
}
```

# client
```

#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <arpa/inet.h>

#define PORT 8080
#define BUFFER_SIZE 1024

int main() {
    int sock;
    struct sockaddr_in address;
    char buffer[BUFFER_SIZE] = {0};
    char response[BUFFER_SIZE] = {0};

    // Creating socket
    if ((sock = socket(AF_INET, SOCK_STREAM, 0)) < 0) {
        perror("Socket creation error");
        exit(EXIT_FAILURE);
    }

    address.sin_family = AF_INET;
    address.sin_port = htons(PORT);

    // Convert IPv4 and IPv6 addresses from text to binary form
    if (inet_pton(AF_INET, "127.0.0.1", &address.sin_addr) <= 0) {
        perror("Invalid address/Address not supported");
        return -1;
    }

    // Connect to server
    if (connect(sock, (struct sockaddr*)&address, sizeof(address)) < 0) {
        perror("Connection Failed");
        return -1;
    }

    // Communication loop
    while (1) {
        printf("Client: ");
        fgets(buffer, BUFFER_SIZE, stdin);
        buffer[strcspn(buffer, "\n")] = '\0'; // Remove newline character
        send(sock, buffer, strlen(buffer), 0);

        // Exit condition
        if (strcmp(buffer, "exit") == 0) {
            printf("Client exiting...\n");
            break;
        }

        memset(response, 0, BUFFER_SIZE);
        int bytes_received = recv(sock, response, BUFFER_SIZE, 0);
        if (bytes_received <= 0) {
            perror("Server disconnected");
            break;
        }
        printf("Server: %s\n", response);
    }

    close(sock);
    return 0;
}

```
