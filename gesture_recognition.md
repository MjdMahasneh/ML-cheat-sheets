# Gesture Recognition Cheatsheet

---

## 1. Input Modalities

- **RGB Video**  
- **Depth Maps**  
- **Skeleton Sequences**

---

## 2. Feature Extraction

- **Hand Keypoints:** use MediaPipe Hands  
- **Optical Flow:** motion features  
- **CNN Features:** 2D/3D CNN on frames or volumes

---

## 3. Temporal Modeling

- **RNN / LSTM / GRU**: sequence modeling  
- **Temporal Convolution**: TCN  
- **Transformer**: self-attention over frames

---

## 4. Classification

- **Softmax**: cross-entropy loss  
- **Metric Learning**: triplet loss

---

## 5. Datasets

- **EgoHands**, **HANDS2017**, **NVIDIA Dynamic Hand Gesture**

