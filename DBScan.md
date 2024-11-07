# DBSCAN Classification of Points

## Problem Statement
Classify the given points as Core Points, Border Points, or Outliers using the **DBSCAN** algorithm.

### Points
\[
(1,1), (1,2), (5,7), (3,1), (3,3), (6,6), (18,4), (18,3), (7,6), (4,3), (4,7), (2,2), (8,6), (8,7), (9,6)
\]

### Parameters
- **Radius (ε)**: 2
- **Minimum number of neighbors (MinPts)**: 3
- **Distance metric**: Manhattan Distance

### Step 1: Calculate Manhattan Distance
The **Manhattan Distance** between two points (x_1, y_1) and (x_2, y_2) is:
\[
\text{distance} = |x_2 - x_1| + |y_2 - y_1|
\]

### Step 2: Find Neighbors for Each Point

| Point     | Neighbors within ε = 2              | Number of Neighbors |
|-----------|-------------------------------------|----------------------|
| (1,1)     | (1,2), (2,2)                        | 2                    |
| (1,2)     | (1,1), (2,2)                        | 2                    |
| (5,7)     | (6,6), (4,7), (7,6), (8,6)          | 4                    |
| (3,1)     | (1,1), (3,3), (2,2)                 | 3                    |
| (3,3)     | (3,1), (4,3), (2,2)                 | 3                    |
| (6,6)     | (5,7), (7,6), (8,6)                 | 3                    |
| (18,4)    | (18,3)                              | 1                    |
| (18,3)    | (18,4)                              | 1                    |
| (7,6)     | (5,7), (6,6), (8,6), (8,7)          | 4                    |
| (4,3)     | (3,3), (4,7), (2,2)                 | 3                    |
| (4,7)     | (5,7), (6,6), (8,6)                 | 3                    |
| (2,2)     | (1,1), (1,2), (3,1), (3,3), (4,3)   | 5                    |
| (8,6)     | (6,6), (7,6), (5,7), (8,7), (9,6)   | 5                    |
| (8,7)     | (8,6), (7,6), (9,6)                 | 3                    |
| (9,6)     | (8,6), (8,7)                        | 2                    |

### Step 3: Classification Based on Neighbors
- **Core Points**: Points with at least 3 neighbors within \epsilon = 2.
- **Border Points**: Points that are within \epsilon of a Core Point but have fewer than 3 neighbors.
- **Outliers**: Points that are neither Core nor Border Points.

#### Classification Results

| Point     | Number of Neighbors | Classification |
|-----------|----------------------|----------------|
| (1,1)     | 2                    | Outlier       |
| (1,2)     | 2                    | Outlier       |
| (5,7)     | 4                    | Core          |
| (3,1)     | 3                    | Core          |
| (3,3)     | 3                    | Core          |
| (6,6)     | 3                    | Core          |
| (18,4)    | 1                    | Outlier       |
| (18,3)    | 1                    | Outlier       |
| (7,6)     | 4                    | Core          |
| (4,3)     | 3                    | Core          |
| (4,7)     | 3                    | Core          |
| (2,2)     | 5                    | Core          |
| (8,6)     | 5                    | Core          |
| (8,7)     | 3                    | Core          |
| (9,6)     | 2                    | Border (connected to Core Point 8,6) |

---

### Summary

- **Core Points**: (5,7), (3,1), (3,3), (6,6), (7,6), (4,3), (4,7), (2,2), (8,6), (8,7)
- **Border Point**: (9,6)
- **Outliers**: (1,1), (1,2), (18,4), (18,3)
