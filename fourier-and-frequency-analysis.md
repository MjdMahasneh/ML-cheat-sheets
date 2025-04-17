# Fourier & Frequency Analysis Cheatsheet

---

## 1. Discrete Fourier Transform (DFT)

**Forward DFT:**  

![X[k]=sum_{n=0}^{N-1} x[n] e^{-j2πkn/N}](https://latex.codecogs.com/gif.latex?X%5Bk%5D%3D%5Csum_%7Bn%3D0%7D%5E%7BN-1%7Dx%5Bn%5De%5E%7B-j%5Cfrac%7B2%5Cpi%7D%7BN%7Dkn%7D)  
Transforms a time-domain signal \(x[n]\) into its frequency-domain representation \(X[k]\).

- Example:  

  ![DFT of [1,0,0,0] is 1 for all k](https://latex.codecogs.com/gif.latex?N%3D4%2C%5C%3Bx%3D%5B1%2C0%2C0%2C0%5D%5Cimplies%20X%5Bk%5D%3D1)

---

**Inverse DFT:**  

![x[n]=1/N sum_{k=0}^{N-1} X[k] e^{j2πkn/N}](https://latex.codecogs.com/gif.latex?x%5Bn%5D%3D%5Cfrac%7B1%7D%7BN%7D%5Csum_%7Bk%3D0%7D%5E%7BN-1%7DX%5Bk%5De%5E%7Bj%5Cfrac%7B2%5Cpi%7D%7BN%7Dkn%7D)  
Recovers the time-domain signal \(x[n]\) from its spectrum \(X[k]\).

- Example:  

  ![IDFT of [1,1,1,1] gives [1,0,0,0]](https://latex.codecogs.com/gif.latex?X%3D%5B1%2C1%2C1%2C1%5D%5Cimplies%20x%5Bn%5D%3D%5B1%2C0%2C0%2C0%5D)

---

## 2. Convolution ⇔ Multiplication

**Time-Domain Convolution:**  

![y[n]=sum x[m] h[n-m]](https://latex.codecogs.com/gif.latex?y%5Bn%5D%3D%5Csum_%7Bm%7Dx%5Bm%5D%5C%2Ch%5Bn-m%5D)  
Linear convolution of input \(x[n]\) with impulse response \(h[n]\).

- Example:  

  ![convolution example](https://latex.codecogs.com/gif.latex?x%3D%5B1%2C2%5D%2C%5C%3Bh%3D%5B1%2C1%5D%5Cimplies%20y%3D%5B1%2C3%2C2%5D)

---

**Frequency-Domain Multiplication:**  

![Y[k] = X[k] * H[k]](https://latex.codecogs.com/gif.latex?Y%5Bk%5D%3DX%5Bk%5D%5Ccdot%20H%5Bk%5D)  
Convolution in time ↔ multiplication in frequency.

---

## 3. Filter Design Basics

**Ideal Low‑Pass Filter (LPF):**  

![Ideal LPF](https://latex.codecogs.com/gif.latex?H%5Bk%5D%3D%5Cbegin%7Bcases%7D1%2C%26%7Ck%7C%5Cle%20k_c%5C%5C0%2C%26%5Ctext%7Botherwise%7D%5Cend%7Bcases%7D)  
Passes frequencies \(|k|\le k_c\).

- **Impulse Response:**  

  ![h[n] = sin(ω_c n)/(π n)](https://latex.codecogs.com/gif.latex?h%5Bn%5D%3D%5Cfrac%7B%5Csin%28%5Comega_c%20n%29%7D%7B%5Cpi%20n%7D)

---

**Ideal High‑Pass Filter (HPF):**  

![Ideal HPF](https://latex.codecogs.com/gif.latex?H%5Bk%5D%3D%5Cbegin%7Bcases%7D0%2C%26%7Ck%7C%5Cle%20k_c%5C%5C1%2C%26%7Ck%7C%3Ek_c%5Cend%7Bcases%7D)

---

**Windowing Method:**  

Create realizable filters by windowing the ideal impulse:  

![h_win[n] = h[n] · w[n]](https://latex.codecogs.com/gif.latex?h_%7B%5Ctext%7Bwin%7D%7D%5Bn%5D%3Dh%5Bn%5D%5Ccdot%20w%5Bn%5D)

- **Hamming Window:**  

  ![Hamming window](https://latex.codecogs.com/gif.latex?w%5Bn%5D%3D0.54-0.46%5Ccos%5Cleft%28%5Cfrac%7B2%5Cpi%20n%7D%7BN-1%7D%5Cright%29)
