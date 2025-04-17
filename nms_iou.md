# NMS & IoU Cheatsheet

---

## 1. Intersection over Union (IoU)

![IoU = area(A∩B)/area(A∪B)](https://latex.codecogs.com/gif.latex?%5Cmathrm%7BIoU%7D%3D%5Cfrac%7B%5Cmathrm%7Barea%7D%28A%5Ccap%20B%29%7D%7B%5Cmathrm%7Barea%7D%28A%5Ccup%20B%29%7D)

- Ranges from 0 (no overlap) to 1 (perfect overlap).

---

## 2. Non-Maximum Suppression (NMS)
1. Sort boxes by confidence score.  
2. Select highest-scoring box, remove it from list and add to output.  
3. Remove all remaining boxes with IoU > threshold wrt selected box.  
4. Repeat until list empty.

- **Threshold:** commonly 0.5.

---

## 3. Example
```text
Boxes: [(x1,y1,x2,y2,score), ...]
Apply NMS yields filtered set.
```
