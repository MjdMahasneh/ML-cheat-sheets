# Morphological Operations Cheatsheet

---

## 1. Basic Ops
- **Erosion:** shrinks bright regions:  
  ![A ⊖ B](https://latex.codecogs.com/gif.latex?A%5Cominus%20B)

- **Dilation:** expands bright regions:  
  ![A ⊕ B](https://latex.codecogs.com/gif.latex?A%5Coplus%20B)


---

## 2. Combined Ops
- **Opening:** erosion then dilation (removes noise)
- **Closing:** dilation then erosion (fills holes)

---

## 3. Morphological Gradient
- <img src="https://latex.codecogs.com/png.latex?(A\oplus%20B)-(A\ominus%20B)" alt="gradient" />

---

## 4. Top-Hat & Black-Hat
- **Top-Hat:** original minus opening (extract small elements)
- **Black-Hat:** closing minus original (extract holes)

