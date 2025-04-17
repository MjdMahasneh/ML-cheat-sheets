# Motion Analysis Cheatsheet

---

## 1. Optical Flow

**Goal:** Estimate pixel motion between frames.

- **Lucas–Kanade:** assumes small motion, solves for displacement in local window.  
  ```text
  ∇I·u = -I_t  →  [sum Ix^2, sum IxIy; sum IxIy, sum Iy^2] [u;v] = -[sum IxIt; sum IyIt]
  ```

- **Horn–Schunck:** global energy minimization with smoothness constraint.  
  ```text
  E = ∫( (I_x u + I_y v + I_t)^2 + λ(|∇u|^2+|∇v|^2) ) dx dy
  ```

**Example:**  
```python
flow = cv2.calcOpticalFlowFarneback(prev_gray, curr_gray, None, ... )
```

---

## 2. Background Subtraction

**Goal:** Separate moving objects from static background.

- **MOG2:** models each pixel with mixture of Gaussians.  
- **KNN:** uses k-nearest neighbors in history.

**Usage:**  
```python
fgmask = backSub.apply(frame)
```

---

## 3. Motion Vectors (Block Matching)

**Goal:** Divide frame into blocks, find best match in next frame by minimizing SAD or SSD.

**Example:**  
```text
for each block B in frame1:
  find shift (dx,dy) that minimizes sum(|B - block_next|).
```

---

## 4. Applications

- **Tracking:** object centroid follows flow vectors.  
- **Stabilization:** estimate global motion, warp frames.  
- **Activity Recognition:** temporal patterns of motion features.  
