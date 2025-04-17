# Image Processing Cheatsheet

---

## 1. Convolution Filters
- **Gaussian Blur:**  
  Kernel: 2D Gaussian, σ parameter  
  - Example: `cv::GaussianBlur(img, dst, Size(5,5), 1.5);`
- **Sharpening:**  
  Kernel: [[0, -1, 0], [-1, 5, -1], [0, -1, 0]]  
- **Edge Detection:**  
  - **Sobel:** `Gx = [[-1,0,1],[-2,0,2],[-1,0,1]]`  
  - **Prewitt:** similar to Sobel with different weights  

---

## 2. Color Space Transforms
- **RGB → Grayscale:**  
  `Y = 0.299R + 0.587G + 0.114B`
- **RGB → HSV:**  
  Use `cv::cvtColor(img, dst, COLOR_BGR2HSV);`

---

## 3. Histogram Operations
- **Equalization:**  
  `cv::equalizeHist(gray, dst);`
- **CLAHE:**  
  `Ptr<CLAHE> clahe = createCLAHE(); clahe->apply(gray, dst);`

---

## 4. Morphological Ops
- **Erosion:**  
  `cv::erode(src, dst, kernel);`
- **Dilation:**  
  `cv::dilate(src, dst, kernel);`
- **Opening/Closing:**  
  Open = erosion then dilation;  
  Close = dilation then erosion.

---

## 5. Geometric Transforms
- **Affine:**  
  `cv::getAffineTransform(srcTri, dstTri)`
- **Perspective (Homography):**  
  `cv::getPerspectiveTransform(src, dst)`
- **Resize:**  
  `cv::resize(src, dst, Size(), fx, fy);`
