# Server 
``` C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <arpa/inet.h>

#define PORT 8080
#define BUFFER_SIZE 1024

int main() {
    int server_fd;
    struct sockaddr_in Server_address, Client_address;
    int addrlen = sizeof(Client_address);
    char buffer[BUFFER_SIZE] = {0};
    char response[BUFFER_SIZE] = {0};

    // Creating socket file descriptor for UDP
    if ((server_fd = socket(AF_INET, SOCK_DGRAM, 0)) == 0) {
        perror("Socket creation failed");
        exit(EXIT_FAILURE);
    }

    Server_address.sin_family = AF_INET;
    Server_address.sin_addr.s_addr = INADDR_ANY;
    Server_address.sin_port = htons(PORT);

    // Binding the socket
    if (bind(server_fd, (struct sockaddr*)&Server_address, sizeof(Server_address)) < 0) {
        perror("Bind failed");
        close(server_fd);
        exit(EXIT_FAILURE);
    }

    printf("Server listening on port %d\n", PORT);

    // Communication loop
    while (1) {
        memset(buffer, 0, BUFFER_SIZE);

        int bytes_read = recvfrom(server_fd, buffer, BUFFER_SIZE, 0, (struct sockaddr*)&Client_address, (socklen_t*)&addrlen);
        if (bytes_read <= 0) {
            perror("Read failed or client disconnected");
            break;
        }

        printf("Client: %s\n", buffer);

        // Exit condition
        if (strcmp(buffer, "exit") == 0) {
            printf("Server exiting...\n");
            break;
        }

        // Prepare response
        printf("Server: ");
        fgets(response, BUFFER_SIZE, stdin);
        response[strcspn(response, "\n")] = '\0'; // Remove newline character

        sendto(server_fd, response, strlen(response), 0, (struct sockaddr*)&Client_address, addrlen);
    }

    // Close socket
    close(server_fd);
    return 0;
}

```

#client
```C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <arpa/inet.h>

#define PORT 8080
#define BUFFER_SIZE 1024

int main() {
    int sock;
    struct sockaddr_in Server_address;
    char buffer[BUFFER_SIZE] = {0};
    char response[BUFFER_SIZE] = {0};
    int addrlen = sizeof(Server_address);

    // Creating socket for UDP
    if ((sock = socket(AF_INET, SOCK_DGRAM, 0)) < 0) {
        perror("Socket creation error");
        exit(EXIT_FAILURE);
    }

    Server_address.sin_family = AF_INET;
    Server_address.sin_port = htons(PORT);

    // Convert IPv4 and IPv6 addresses from text to binary form
    if (inet_pton(AF_INET, "127.0.0.1", &Server_address.sin_addr) <= 0) {
        perror("Invalid address/Address not supported");
        return -1;
    }

    // Communication loop
    while (1) {
        printf("Client: ");
        fgets(buffer, BUFFER_SIZE, stdin);
        buffer[strcspn(buffer, "\n")] = '\0'; // Remove newline character

        sendto(sock, buffer, strlen(buffer), 0, (struct sockaddr*)&Server_address, addrlen);

        // Exit condition
        if (strcmp(buffer, "exit") == 0) {
            printf("Client exiting...\n");
            break;
        }

        memset(response, 0, BUFFER_SIZE);

        int bytes_received = recvfrom(sock, response, BUFFER_SIZE, 0, (struct sockaddr*)&Server_address, (socklen_t*)&addrlen);
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
