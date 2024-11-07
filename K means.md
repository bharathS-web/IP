### Step 1: Calculate Manhattan Distances from Each Point to Initial Centroids (C1 and C2)

#### Manhattan Distance Formula:
\[
\text{Manhattan Distance} = |x_1 - x_2| + |y_1 - y_2|
\]

| Point | Distance to C1 (3,4) | Distance to C2 (9,8) |
|-------|----------------------|----------------------|
| A     | 3                    | 13                   |
| B     | 2                    | 8                    |
| C     | 6                    | 8                    |
| D     | 6                    | 8                    |
| E     | 4                    | 6                    |
| F     | 7                    | 5                    |
| G     | 4                    | 6                    |
| H     | 9                    | 5                    |
| I     | 9                    | 3                    |
| J     | 11                   | 5                    |
| K     | 5                    | 5                    |
| L     | 6                    | 4                    |

### Step 2: Assign Points to the Nearest Centroid (C1 or C2)

- **Points assigned to C1 (3,4)**: A, B, C, D, E, G, K, L
- **Points assigned to C2 (9,8)**: F, H, I, J

### Step 3: Calculate New Centroids

#### New C1 Centroid (Cluster 1):

- Points in Cluster 1: A (2,2), B (3,6), C (3,10), D (3,10), E (3,8), G (5,6), K (7,5), L (8,5)

Average of x-coordinates:
\[
\frac{2 + 3 + 3 + 3 + 3 + 5 + 7 + 8}{8} = \frac{34}{8} = 4.25 \approx 4
\]

Average of y-coordinates:
\[
\frac{2 + 6 + 10 + 10 + 8 + 6 + 5 + 5}{8} = \frac{52}{8} = 6.5 \approx 7
\]

**New C1 = (4,7)**

#### New C2 Centroid (Cluster 2):

- Points in Cluster 2: F (5,9), H (6,10), I (7,9), J (7,11)

Average of x-coordinates:
\[
\frac{5 + 6 + 7 + 7}{4} = \frac{25}{4} = 6.25 \approx 6
\]

Average of y-coordinates:
\[
\frac{9 + 10 + 9 + 11}{4} = \frac{39}{4} = 9.75 \approx 10
\]

**New C2 = (6,10)**

### Step 4: Reassign Points to the Nearest Centroid Using Updated Centroids

#### Distances from New C1 (4,7):

| Point | Distance to C1 (4,7) |
|-------|----------------------|
| A     | 3                    |
| B     | 3                    |
| C     | 3                    |
| D     | 3                    |
| E     | 1                    |
| G     | 2                    |
| K     | 3                    |
| L     | 4                    |

#### Distances from New C2 (6,10):

| Point | Distance to C2 (6,10) |
|-------|-----------------------|
| F     | 2                     |
| H     | 1                     |
| I     | 1                     |
| J     | 2                     |

### Step 5: Final Clusters

- **Cluster 1 (C1)**: A, B, C, D, E, G, K, L
- **Cluster 2 (C2)**: F, H, I, J

### Final Centroids:
- **C1 = (4,7)**
- **C2 = (6,10)**

### Final Clustering:

- **Cluster 1**: A (2,2), B (3,6), C (3,10), D (3,10), E (3,8), G (5,6), K (7,5), L (8,5)
- **Cluster 2**: F (5,9), H (6,10), I (7,9), J (7,11)
