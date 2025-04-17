# Clustering Methods Cheatsheet

---

## 1. k-Means

**Intuition:** Partition data into k clusters by assigning each point to the nearest cluster center, then update centers to the mean of assigned points.  
- **Algorithm Steps:**  
  1. Initialize k centroids (randomly or k-means++).  
  2. **Assign:** each point → nearest centroid.  
  3. **Update:** centroid = mean of assigned points.  
  4. Repeat until convergence.  

**Example:**  
```text
Points: [(1,1), (2,1), (4,5), (5,4)], k=2
Initial centroids: (1,1), (5,4)
Assignments → update → converge to clusters around (1.5,1) and (4.5,4.5)
```

**Pros/Cons:**  
- Fast, simple.  
- Assumes spherical clusters, sensitive to initialization, k must be chosen.

---

## 2. Hierarchical Clustering

**Intuition:** Builds a tree (dendrogram) of clusters by merging or splitting.  
- **Agglomerative (bottom-up):** start with each point as a cluster, merge closest pairs.  
- **Divisive (top-down):** start with all points, split clusters recursively.  

**Linkages:** single (min distance), complete (max), average (mean).  
- **Example (Agglomerative):** merge closest points until desired cluster count.

---

## 3. DBSCAN

**Intuition:** Groups points with high local density; noise points are outliers.  
- **Parameters:** ε (radius), minPts (minimum points in ε).  
- **Core Point:** ≥ minPts within ε radius.  
- **Border Point:** within ε of a core point but < minPts.  
- **Noise:** neither core nor border.  

**Example:**  
```text
ε=0.5, minPts=5 on spatial data → clusters of dense regions, outliers removed.
```

**Pros/Cons:**  
- Finds arbitrarily shaped clusters, robust to outliers.  
- Sensitive to ε, struggles with varying density.

---

## 4. Gaussian Mixture Models (GMM)

**Intuition:** Models data as a mixture of Gaussian distributions. Soft assignment of points to components.  
- **Expectation-Maximization (EM):**  
  1. **E-step:** compute probabilities (responsibilities) of each component generating each point.  
  2. **M-step:** update means, covariances, and mixing weights.  

**Example:**  
```text
2D data → fit 3 Gaussians, get probability for each cluster, cluster by max probability.
```

**Pros/Cons:**  
- Captures elliptical clusters, provides probabilities.  
- Can overfit, requires careful covariance regularization.

---

## 5. Evaluation Metrics

- **Silhouette Score:** measures cohesion vs separation.  
- **Davies–Bouldin Index:** average similarity between clusters (lower is better).  
- **Elbow Method:** plot inertia vs k to pick elbow point.  
