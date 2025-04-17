# Face Recognition & Landmarks Cheatsheet

---

## 1. Face Detection

- **Haar Cascades:** `cv2.CascadeClassifier`  
- **DNN Models:** `cv2.dnn.readNetFromCaffe`

---

## 2. Landmark Detection

- **dlib 68-point:**  
  ```python
  import dlib
  predictor = dlib.shape_predictor("shape_68.dat")
  landmarks = predictor(gray, rect)
  ```
- **MediaPipe Face Mesh:** 468 landmarks

---

## 3. Face Embeddings

- **Models:** FaceNet, ArcFace  
- **Compute Embedding:**  
  ```python
  embedding = model.predict(face_img)
  ```

---

## 4. Recognition

- **Distance Metric:** cosine / Euclidean  
- **Thresholding:** match if distance < thresh  

---

## 5. Alignment

- **Affine Transform:** align eyes and mouth  
- **Warp:** `cv2.getAffineTransform`, `cv2.warpAffine`

