# Depth Estimation Cheatsheet

---

## 1. Stereo Geometry
- Depth from disparity: d = f * B / disparity
- f: focal length, B: baseline

---

## 2. Monocular Methods
- Use deep nets to predict depth map.
- Loss: scale-invariant, L1, gradient loss.

---

## 3. Sensors
- LiDAR vs stereo: sparse vs dense
- RGB-D cameras: structured light, time-of-flight

---

## 4. Post-processing
- Median filtering, hole filling.

---
