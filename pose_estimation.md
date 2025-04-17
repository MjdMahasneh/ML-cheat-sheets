# Pose Estimation Cheatsheet

---

## 1. Keypoint Detection

- **Common Models:**  
  - OpenPose (COCO, MPII)  
  - BlazePose (MediaPipe)  

- **Pipeline Steps:**  
  1. Person detection  
  2. Keypoint heatmap regression  
  3. Post-process: decode skeleton  

---

## 2. Coordinate Conventions

- **2D:** (x, y) in image pixels  
- **3D:** (X, Y, Z) in camera space, use PnP  

---

## 3. OpenCV PnP

- **Solve PnP:**  
  ```python
  _, rvec, tvec = cv2.solvePnP(obj_pts, img_pts, K, dist)
  ```
- **Project Points:**  
  ```python
  img_pts, _ = cv2.projectPoints(obj_pts, rvec, tvec, K, dist)
  ```

---

## 4. MediaPipe BlazePose

- **Python API:**  
  ```python
  import mediapipe as mp
  mp_pose = mp.solutions.pose.Pose()
  results = mp_pose.process(image)
  landmarks = results.pose_landmarks
  ```

---

## 5. Evaluation Metrics

- **PCK (Percentage of Correct Keypoints):** threshold-based accuracy  
- **MPJPE (Mean Per Joint Position Error):** for 3D pose  

