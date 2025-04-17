# Video Processing Cheatsheet

---

## 1. Frame Operations
- **Capture:**  
  `VideoCapture cap("video.mp4");`
- **Read Frame:**  
  `cap >> frame;`
- **Frame Rate:**  
  `double fps = cap.get(CAP_PROP_FPS);`

---

## 2. Codecs & I/O
- **Writer:**  
  `VideoWriter writer("out.avi", fourcc, fps, Size(w,h));`
- **FourCC:**  
  `int fourcc = VideoWriter::fourcc('M','J','P','G');`

---

## 3. Motion Analysis
- **Optical Flow (Farneback):**  
  `calcOpticalFlowFarneback(prev, next, flow, ...);`
- **Background Subtraction:**  
  `Ptr<BackgroundSubtractor> p = createBackgroundSubtractorMOG2();`

---

## 4. Tracking
- **KLT Tracker:**  
  `calcOpticalFlowPyrLK(...)`
- **Object Trackers:**  
  `Ptr<Tracker> tracker = TrackerKCF::create();`

---

## 5. Video Stabilization
- Estimate transformation between frames, apply warpPerspective.

