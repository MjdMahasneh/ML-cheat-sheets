# OpenCV Function Quick‑Ref

---

## 1. cv::Mat Basics
- Create: `cv::Mat img(rows, cols, CV_8UC3);`
- Access: `img.at<Vec3b>(y,x)`, `img.data`

---

## 2. I/O & Display
- Read: `cv::imread("file.jpg", cv::IMREAD_COLOR);`
- Write: `cv::imwrite("out.png", img);`
- Show: `cv::imshow("win", img); cv::waitKey(0);`

---

## 3. Color & Filtering
- Convert: `cv::cvtColor(src, dst, cv::COLOR_BGR2GRAY);`
- Blur: `cv::GaussianBlur(src, dst, Size(5,5), 1.5);`
- Edge: `cv::Canny(src, dst, 100, 200);`
- Threshold: `cv::threshold(src, dst, 128, 255, cv::THRESH_BINARY);`

---

## 4. Keypoints & Descriptors
- Detector: `Ptr<ORB> orb = ORB::create();`
- `orb->detect(img, keypoints);`
- `orb->compute(img, keypoints, descriptors);`

---

## 5. Feature Matching
- BFMatcher: `BFMatcher matcher(NORM_HAMMING);`
- `matcher.match(desc1, desc2, matches);`

---
