# K-Medoid Clustering Problem

Given the following points:

| Point | Coordinates |
|-------|-------------|
| A1    | (2, 6)      |
| A2    | (3, 8)      |
| A3    | (4, 7)      |
| A4    | (6, 2)      |
| A5    | (6, 4)      |
| A6    | (7, 3)      |
| A7    | (7, 4)      |
| A8    | (8, 5)      |
| A9    | (7, 6)      |
| A10   | (3, 4)      |

### Medoid Combinations:

1) **M1 = A2 (3,8) and M2 = A6 (7,3)**
2) **M1 = A2 (3,8) and M2 = A7 (7,4)**
3) **M1 = A2 (3,8) and M2 = A5 (7,3)**

We will calculate the distance for each combination using **Manhattan Distance** and assign clusters to the points.

## Manhattan Distance Formula:
\[
\text{Manhattan Distance} = |x_1 - x_2| + |y_1 - y_2|
\]

### 1) **M1 = A2 (3,8) and M2 = A6 (7,3)**

| Point | Distance to A2 | Distance to A6 |
|-------|----------------|----------------|
| A1    | 3              | 5              |
| A2    | 0              | 4              |
| A3    | 2              | 4              |
| A4    | 5              | 2              |
| A5    | 4              | 1              |
| A6    | 4              | 0              |
| A7    | 5              | 1              |
| A8    | 7              | 3              |
| A9    | 5              | 3              |
| A10   | 4              | 5              |

#### Cluster Assignment for M1 = A2 and M2 = A6:

- Cluster 1 (A2) includes: **A1, A2, A3, A10** (Closest to A2)
- Cluster 2 (A6) includes: **A4, A5, A6, A7, A8, A9** (Closest to A6)

**Total Distance** = **21**.

---

### 2) **M1 = A2 (3,8) and M2 = A7 (7,4)**

| Point | Distance to A2 | Distance to A7 |
|-------|----------------|----------------|
| A1    | 3              | 5              |
| A2    | 0              | 4              |
| A3    | 2              | 4              |
| A4    | 5              | 3              |
| A5    | 4              | 1              |
| A6    | 4              | 3              |
| A7    | 4              | 0              |
| A8    | 7              | 2              |
| A9    | 5              | 3              |
| A10   | 4              | 5              |

#### Cluster Assignment for M1 = A2 and M2 = A7:

- Cluster 1 (A2) includes: **A1, A2, A3, A10** (Closest to A2)
- Cluster 2 (A7) includes: **A4, A5, A6, A7, A8, A9** (Closest to A7)

**Total Distance** = **22**.

---

### 3) **M1 = A2 (3,8) and M2 = A5 (7,3)**

| Point | Distance to A2 | Distance to A5 |
|-------|----------------|----------------|
| A1    | 3              | 5              |
| A2    | 0              | 4              |
| A3    | 2              | 4              |
| A4    | 5              | 5              |
| A5    | 4              | 0              |
| A6    | 4              | 2              |
| A7    | 5              | 3              |
| A8    | 7              | 3              |
| A9    | 5              | 3              |
| A10   | 4              | 5              |

#### Cluster Assignment for M1 = A2 and M2 = A5:

- Cluster 1 (A2) includes: **A1, A2, A3, A10** (Closest to A2)
- Cluster 2 (A5) includes: **A4, A5, A6, A7, A8, A9** (Closest to A5)

**Total Distance** = **24**.

---

### Best Clustering:

- **For M1 = A2 and M2 = A6**, the total distance is **21**.
- **For M1 = A2 and M2 = A7**, the total distance is **22**.
- **For M1 = A2 and M2 = A5**, the total distance is **24**.

**Best Clustering**: The combination **M1 = A2 and M2 = A6** gives the **best clustering**, with the lowest total distance of **21**.
