# Convolutional Attention Cheatsheet

---

## 1. Spatial Attention
- Compute feature map average & max along channel → two 2D maps.
- Concat, apply conv (7×7), sigmoid → spatial attention map.

---

## 2. Channel Attention
- Global avg & max pool → two vectors.
- Shared MLP → two feature vectors.
- Sum, sigmoid → channel attention weights.

---

## 3. CBAM Module
```text
F' = M_c(F) ⊗ F
F'' = M_s(F') ⊗ F'
```
Where M_c = channel, M_s = spatial attention.

---

## 4. Bottleneck Attention
- Insert after residual blocks.
- Light-weight conv + gating.

---
