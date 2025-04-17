# LiDAR Processing Cheatsheet

---

## 1. Point Cloud Basics
- **Load/Save:**  
  PCD/PLY formats using PCL library.
- **Access Points:**  
  `cloud->points[i].x/y/z`

---

## 2. Filtering
- **Voxel Grid Downsampling:**  
  `VoxelGrid<PointXYZ> vg; vg.setLeafSize(...);`
- **Statistical Outlier Removal:**  
  `StatisticalOutlierRemoval<PointXYZ> sor;`

---

## 3. Segmentation
- **Plane Segmentation (RANSAC):**  
  `SACSegmentation<PointXYZ> seg;`
- **Cluster Extraction:**  
  `EuclideanClusterExtraction<PointXYZ> ec;`

---

## 4. Feature Extraction
- **Normals:**  
  `NormalEstimation<PointXYZ, Normal> ne;`
- **Descriptors:**  
  FPFH, PFH

---

## 5. Registration
- **ICP:**  
  `IterativeClosestPoint<PointXYZ, PointXYZ> icp;`

