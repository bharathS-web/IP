
# Agglomerative Clustering

## 1. Complete Linkage Clustering

### Initial Distance Matrix

|     | A  | B  | C  | D  | E  |
|-----|----|----|----|----|----|
| **A** | 0  | 10 | 4  | 7  | 12 |
| **B** | 10 | 0  | 8  | 6  | 11 |
| **C** | 4  | 8  | 0  | 10 | 3  |
| **D** | 7  | 6  | 10 | 0  | 9  |
| **E** | 12 | 11 | 3  | 9  | 0  |

### Clustering Steps (Complete Linkage)

1. **Step 1: Merge (C, E)** with distance 3.
   - Calculate the maximum distance between the points in clusters C and E:
     - Max distance between C and E = 3 (Distance between C and E).
   - **New Distance Matrix** (after merging C and E):
   
   |     | A  | B  | D  | CE |
   |-----|----|----|----|----|
   | **A** | 0  | 10 | 7  | 12 |
   | **B** | 10 | 0  | 6  | 11 |
   | **D** | 7  | 6  | 0  | 9  |
   | **CE**| 12 | 11 | 9  | 0  |

2. **Step 2: Merge (B, D)** with distance 6.
   - Calculate the maximum distance between the points in clusters B and D:
     - Max distance between B and D = 6 (Distance between B and D).
   - **New Distance Matrix** (after merging B and D):
   
   |     | A  | BD | CE |
   |-----|----|----|----|
   | **A** | 0  | 10 | 12 |
   | **BD**| 10 | 0  | 11 |
   | **CE**| 12 | 11 | 0  |

3. **Step 3: Merge (A, BD)** with distance 10.
   - Calculate the maximum distance between the points in clusters A and BD:
     - Max distance between A and BD = 10 (Distance between A and B).
   - **New Distance Matrix** (after merging A and BD):
   
   |     | ABD | CE |
   |-----|-----|----|
   | **ABD** | 0   | 12 |
   | **CE**  | 12  | 0  |

4. **Step 4: Merge (ABD, CE)** with distance 12.
   - Calculate the maximum distance between the points in clusters ABD and CE:
     - Max distance between ABD and CE = 12 (Distance between A and E).
     
### Complete Linkage Dendrogram

┌─── A
   │

┌───┤ │   │     ┌─── B │   │     │ │   └─────┤ │         │     ┌─── D │         │     │ └─────────┤     └───── C │ └───── E

---

## 2. Average Linkage Clustering

### Initial Distance Matrix

|     | A  | B  | C  | D  | E  |
|-----|----|----|----|----|----|
| **A** | 0  | 10 | 4  | 7  | 12 |
| **B** | 10 | 0  | 8  | 6  | 11 |
| **C** | 4  | 8  | 0  | 10 | 3  |
| **D** | 7  | 6  | 10 | 0  | 9  |
| **E** | 12 | 11 | 3  | 9  | 0  |

### Clustering Steps (Average Linkage)

1. **Step 1: Merge (C, E)** with distance 3.
   - Calculate the average distance between points in clusters C and E:
     - Average distance between C and E = (3 + 12) / 2 = 7.5.
   - **New Distance Matrix** (after merging C and E):
   
   |     | A  | B  | D  | CE |
   |-----|----|----|----|----|
   | **A** | 0  | 10 | 7  | 8  |
   | **B** | 10 | 0  | 6  | 9.5|
   | **D** | 7  | 6  | 0  | 9.5|
   | **CE**| 8  | 9.5| 9.5| 0  |

2. **Step 2: Merge (A, D)** with distance 7.
   - Calculate the average distance between points in clusters A and D:
     - Average distance between A and D = (7 + 6) / 2 = 6.5.
   - **New Distance Matrix** (after merging A and D):
   
   |     | AD | B  | CE |
   |-----|----|----|----|
   | **AD** | 0  | 8  | 8.75|
   | **B**  | 8  | 0  | 9.5 |
   | **CE** | 8.75| 9.5| 0  |

3. **Step 3: Merge (AD, B)** with distance 8.
   - Calculate the average distance between points in clusters AD and B:
     - Average distance between AD and B = (8 + 8) / 2 = 8.
   - **New Distance Matrix** (after merging AD and B):
   
   |     | ADB | CE |
   |-----|-----|----|
   | **ADB** | 0   | 9.125 |
   | **CE**  | 9.125| 0     |

4. **Step 4: Merge (ADB, CE)** with distance 9.125.
   - Calculate the average distance between points in clusters ADB and CE:
     - Average distance between ADB and CE = (9.125 + 12) / 2 = 10.0625.
     
### Average Linkage Dendrogram

┌─── A
   │

┌───┤ │   │     ┌─── D │   │     │ └───┤     └───── B │ └─────────── C │ └───── E



