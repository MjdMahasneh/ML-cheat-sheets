# Camera & Projection Models Cheatsheet

---

## 1. Pinhole Camera Model

**Projection Equation:**  
<img src="https://latex.codecogs.com/png.latex?\begin{bmatrix}u\\v\\1\end{bmatrix}=\frac{1}{Z}\,K\,[R\;|\;t]\,\begin{bmatrix}X\\Y\\Z\\1\end{bmatrix}" alt="Pinhole equation" />

- **Intrinsic Matrix (K):**  
  \[
  K=\begin{bmatrix}
  f_x & 0   & c_x\\
  0   & f_y & c_y\\
  0   & 0   & 1
  \end{bmatrix}
  \]

- **Extrinsic ([R|t]):**  
  Combines rotation (R) and translation (t) from world to camera.

---

## 2. Lens Distortion

**Radial:**  
<img src="https://latex.codecogs.com/png.latex?r_d=r(1+k_1r^2+k_2r^4+k_3r^6)" alt="radial distortion" />

**Tangential:**  
<img src="https://latex.codecogs.com/png.latex?x_d=x+2p_1xy+p_2(r^2+2x^2)" alt="tangential distortion" />

- Corrected via OpenCV’s `undistort` functions.

---

## 3. Calibration

- **Chessboard Method:** detect corners, solve for K, distortion.
- **Functions:** `cv::calibrateCamera`, `cv::undistort`, `cv::initUndistortRectifyMap`

---
