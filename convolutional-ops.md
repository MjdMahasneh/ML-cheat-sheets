# Convolutional Ops in CV Cheatsheet

---

## 1. 2D Convolution

**Operation:**  
<img src="https://latex.codecogs.com/png.latex?Y[i,j]=\sum_{m=0}^{k-1}\sum_{n=0}^{k-1}K[m,n]\;X[i+m,j+n]" alt="Y[i,j]=sum over m,n K[m,n] X[i+m,j+n]" />

Sliding a *k×k* kernel **K** over input **X** to produce feature map **Y**.

- **Example:**  
  ```text
  X = [[1,2,3],
       [4,5,6],
       [7,8,9]]
  K = [[0,1],
       [2,3]]
  
  Y[0,0] = 0*1 + 1*2 + 2*4 + 3*5 = 2 + 8 + 15 = 25
  ```

---

## 2. Output Size

**Formula:**  

![H_out = ⌊(H+2P–K)/S⌋ + 1, W_out = ⌊(W+2P–K)/S⌋ + 1](https://latex.codecogs.com/gif.latex?H_%7Bout%7D%3D%5Cleft%5Clfloor%5Cfrac%7BH%2B2P-K%7D%7BS%7D%5Cright%5Crfloor%2B1%2C%5Cquad%20W_%7Bout%7D%3D%5Cleft%5Clfloor%5Cfrac%7BW%2B2P-K%7D%7BS%7D%5Cright%5Crfloor%2B1)


- **Parameters:**  
  - **H, W**: input height & width  
  - **K**: kernel size  
  - **P**: padding  
  - **S**: stride  

- **Example:**  
  ```text
  H=32, W=32, K=5, P=0, S=1
  H_out = floor((32 + 2*0 - 5)/1) + 1 = 28
  W_out = floor((32 + 2*0 - 5)/1) + 1 = 28
  ```

---

## 3. Padding

- **Valid (no padding):** P = 0  
  ```text
  H_out = floor((H + 2*0 - K)/S) + 1
  ```

- **Same (preserve size):** P = floor(K/2)  
  ```text
  K = 5  ->  P = 2
  H_out = floor((32 + 2*2 - 5)/1) + 1 = 32
  ```

---

## 4. Stride

Controls the step between kernel applications.

- **Stride = 1:** covers every position  
- **Stride = 2:** skips one pixel  

- **Example:**  
  ```text
  H = 5, K = 3, P = 0, S = 2
  H_out = floor((5 + 2*0 - 3)/2) + 1 = 2
  Output size = 2 × 2
  ```

---

## 5. Pooling

**Max Pool (k×k, stride S):**  

![Y[i,j] = max_{0≤m,n<k} X[iS+m, jS+n]](https://latex.codecogs.com/gif.latex?Y%5Bi%2Cj%5D%3D%5Cmax_%7B0%5Cle%20m%2Cn%3Ck%7DX%5BiS%2Bm%2C%20jS%2Bn%5D)

- **Example (2×2, S=2):**  
  ```text
  X = [[ 1,  3,  2,  4],
       [ 5,  6,  7,  8],
       [ 9, 10, 11, 12],
       [13, 14, 15, 16]]

  Y = [[6,  8],
       [14, 16]]
  ```

---

**Average Pool (k×k, stride S):**  
<img src="https://latex.codecogs.com/png.latex?Y[i,j]=\frac{1}{k^2}\sum_{m,n}X[i\,S+m,\;j\,S+n]" alt="Y[i,j]=average over k×k window" />

- **Example (2×2, S=2):**  
  ```text
  Y = [[(1+3+5+6)/4, (2+4+7+8)/4],
       [(9+10+13+14)/4, (11+12+15+16)/4]]
    = [[3.75, 5.25],
       [11.50, 13.50]]
  ```
