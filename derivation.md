# Derivation Cheatsheet for Machine Learning

---

## 1. Scalar Derivatives
- **Constant:**  
  ![d/dx c = 0](https://latex.codecogs.com/gif.latex?%5Cfrac%7Bd%7D%7Bdx%7Dc%3D0)  
  Example:  
  ![d/dx (5) = 0](https://latex.codecogs.com/gif.latex?%5Cfrac%7Bd%7D%7Bdx%7D%285%29%3D0)

- **Power:**  
  ![d/dx x^n = n x^{n-1}](https://latex.codecogs.com/gif.latex?%5Cfrac%7Bd%7D%7Bdx%7Dx%5En%3Dn%5C%2Cx%5E%7Bn-1%7D)  
  Example:  
  ![d/dx (x^3) = 3x^2](https://latex.codecogs.com/gif.latex?%5Cfrac%7Bd%7D%7Bdx%7D%28x%5E3%29%3D3x%5E2)

- **Constant Multiple:**  
  ![d/dx (a x) = a](https://latex.codecogs.com/gif.latex?%5Cfrac%7Bd%7D%7Bdx%7D%28a%5C%2Cx%29%3Da)  
  Example:  
  ![d/dx (4x) = 4](https://latex.codecogs.com/gif.latex?%5Cfrac%7Bd%7D%7Bdx%7D%284x%29%3D4)

- **Trigonometric:**  
  ![d/dx sin x = cos x](https://latex.codecogs.com/gif.latex?%5Cfrac%7Bd%7D%7Bdx%7D%5Csin%20x%3D%5Ccos%20x)  
  Example:  
  ![d/dx sin(x) = cos(x)](https://latex.codecogs.com/gif.latex?%5Cfrac%7Bd%7D%7Bdx%7D%5Csin%28x%29%3D%5Ccos%28x%29)

- **Exponential:**  
  ![d/dx e^x = e^x](https://latex.codecogs.com/gif.latex?%5Cfrac%7Bd%7D%7Bdx%7De%5Ex%3De%5Ex)  
  Example:  
  ![d/dx e^2 = e^2](https://latex.codecogs.com/gif.latex?%5Cfrac%7Bd%7D%7Bdx%7De%5E2%3De%5E2)

---

## 2. Basic Rules
**Sum Rule:**  
![d/dx [f+g] = f' + g'](https://latex.codecogs.com/gif.latex?%5Cfrac%7Bd%7D%7Bdx%7D%5Bf%2Bg%5D%3Df%27%2Bg%27)  

- Example:  
  ![d/dx (x^2+e^x) = 2x + e^x](https://latex.codecogs.com/gif.latex?%5Cfrac%7Bd%7D%7Bdx%7D%28x%5E2%2Be%5Ex%29%3D2x%2Be%5Ex)

**Product Rule:**  
![d/dx [f g] = f' g + f g'](https://latex.codecogs.com/gif.latex?%5Cfrac%7Bd%7D%7Bdx%7D%5Bf%5C%2Cg%5D%3Df%27%5C%2Cg%2Bf%5C%2Cg%27)  

- Example:  
  ![d/dx (x^2 sin x) = 2x sin x + x^2 cos x](https://latex.codecogs.com/gif.latex?%5Cfrac%7Bd%7D%7Bdx%7D%28x%5E2%5Csin%20x%29%3D2x%5Csin%20x%2Bx%5E2%5Ccos%20x)

**Quotient Rule:**  
![d/dx [f/g] = (f' g - f g') / g^2](https://latex.codecogs.com/gif.latex?%5Cfrac%7Bd%7D%7Bdx%7D%5Bf%2Fg%5D%3D%5Cfrac%7Bf%27%5C%2Cg%20-%20f%5C%2Cg%27%7D%7Bg%5E2%7D)  

- Example:  
  ![d/dx ((x+1)/(x-1)) = -2/(x-1)^2](https://latex.codecogs.com/gif.latex?%5Cfrac%7Bd%7D%7Bdx%7D%5Cfrac%7Bx%2B1%7D%7Bx-1%7D%3D-%5Cfrac%7B2%7D%7B%28x-1%29%5E2%7D)

**Chain Rule:**  
![d/dx f(g(x)) = f'(g(x)) g'(x)](https://latex.codecogs.com/gif.latex?%5Cfrac%7Bd%7D%7Bdx%7Df%28g%28x%29%29%3Df%27%28g%28x%29%29%5C%2Cg%27%28x%29)  

- Example:  
  ![d/dx sin(x^2) = 2x cos(x^2)](https://latex.codecogs.com/gif.latex?%5Cfrac%7Bd%7D%7Bdx%7D%5Csin%28x%5E2%29%3D2x%5Ccos%28x%5E2%29)

---

## 3. Partial Derivatives
- **Definition:**  
  ![∂/∂x_i f(x1…xn)](https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cpartial%7D%7B%5Cpartial%20x_i%7Df%28x_1%2C%5Cdots%2Cx_n%29)

- **Example (f(x,y)=x^2y):**  
  ![∂f/∂x = 2xy, ∂f/∂y = x^2](https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cpartial%20f%7D%7B%5Cpartial%20x%7D%3D2xy%2C%5Cquad%5Cfrac%7B%5Cpartial%20f%7D%7B%5Cpartial%20y%7D%3Dx%5E2)

---

## 4. Vector Derivatives
- **Gradient:**  
  ![∇f = [∂x f; ∂y f]](https://latex.codecogs.com/gif.latex?%5Cnabla%20f%3D%5Cbegin%7Bbmatrix%7D%5Cpartial_x%20f%5C%5C%5Cpartial_y%20f%5Cend%7Bbmatrix%7D)  
  Example:  
  ![∇f = [2x; 2y]](https://latex.codecogs.com/gif.latex?f%28x%2Cy%29%3Dx%5E2%2By%5E2%5Cimplies%5Cnabla%20f%3D%5Cbegin%7Bbmatrix%7D2x%5C%5C2y%5Cend%7Bbmatrix%7D)

- **Jacobian:**  
  ![J_ij = ∂ f_i / ∂ x_j](https://latex.codecogs.com/gif.latex?J_%7Bij%7D%3D%5Cfrac%7B%5Cpartial%20f_i%7D%7B%5Cpartial%20x_j%7D)  
  Example:  
  ![J = [[1,1],[1,-1]]](https://latex.codecogs.com/gif.latex?f%28%5Bx%2Cy%5D%29%3D%5Bx%2By%2Cx-y%5D%5Cimplies%20J%3D%5Cbegin%7Bbmatrix%7D1%261%5C%5C1%26-1%5Cend%7Bbmatrix%7D)

- **Hessian:**  
  ![H_ij = ∂^2 f / ∂ x_i ∂ x_j](https://latex.codecogs.com/gif.latex?H_%7Bij%7D%3D%5Cfrac%7B%5Cpartial%5E2%20f%7D%7B%5Cpartial%20x_i%5Cpartial%20x_j%7D)  
  Example:  
  ![H = [[0,1],[1,0]]](https://latex.codecogs.com/gif.latex?f%28x%2Cy%29%3Dxy%5Cimplies%20H%3D%5Cbegin%7Bbmatrix%7D0%261%5C%5C1%260%5Cend%7Bbmatrix%7D)

---

## 5. Common ML Functions
- **Sigmoid:**  
  ![σ(z)=1/(1+e^{-z}), σ'(z)=σ(z)(1-σ(z))](https://latex.codecogs.com/gif.latex?%5Csigma%28z%29%3D%5Cfrac%7B1%7D%7B1%2Be%5E%7B-z%7D%7D%2C%5C%3B%5Csigma%27%28z%29%3D%5Csigma%28z%29%281-%5Csigma%28z%29%29)  
  Example:  
  ![σ(0)=0.5, σ'(0)=0.25](https://latex.codecogs.com/gif.latex?%5Csigma%280%29%3D0.5%2C%5C%3B%5Csigma%27%280%29%3D0.25)

- **Softmax:**  
  ![s_i = e^{z_i}/∑_j e^{z_j}, ∂ s_i/∂ z_j = s_i(δ_ij - s_j)](https://latex.codecogs.com/gif.latex?s_i%3D%5Cfrac%7Be%5E%7Bz_i%7D%7D%7B%5Csum_j%20e%5E%7Bz_j%7D%7D%2C%5C%3B%5Cfrac%7B%5Cpartial%20s_i%7D%7B%5Cpartial%20z_j%7D%3Ds_i%28%5Cdelta_%7Bij%7D-s_j%29)  
  Example:  
  ![z=[1,2] ⇒ s≈[0.27,0.73]](https://latex.codecogs.com/gif.latex?z%3D%5B1%2C2%5D%5Cimplies%20s%5Capprox%5B0.27%2C0.73%5D)

- **MSE Loss:**  
  ![L=½(y − ŷ)², ∂_{ŷ}L = ŷ − y](https://latex.codecogs.com/gif.latex?L%3D%5Ctfrac%7B1%7D%7B2%7D%28y-%5Chat%20y%29%5E2%2C%20%5Cpartial_%7B%5Chat%20y%7DL%3D%5Chat%20y-y)  
  **Example:**  
  ![y=3, ŷ=2 ⇒ L=0.5, ∂L=−1](https://latex.codecogs.com/gif.latex?y%3D3%2C%20%5Chat%20y%3D2%20%5Cimplies%20L%3D0.5%2C%20%5Cpartial%20L%3D-1)

- **Cross-Entropy:**  
  ![L=-[y ln p + (1-y) ln(1-p)], ∂_p L = (p-y)/(p(1-p))](https://latex.codecogs.com/gif.latex?L%3D-%5By%20ln%20p%20%2B%20%281-y%29%20ln%281-p%29%5D%2C%5C%3B%5Cpartial_pL%3D%5Cfrac%7Bp-y%7D%7Bp%281-p%29%7D)  
  Example:  
  ![y=1, p=0.9 ⇒ L≈0.105, ∂_pL≈-1.11](https://latex.codecogs.com/gif.latex?y%3D1%2Cp%3D0.9%5Cimplies%20L%5Capprox0.105%2C%5C%3B%5Cpartial_pL%5Capprox-1.11)

---

## 6. Backpropagation Snippet
If z=Wx+b and δ = ∂_z L, then:  
![∂_W L = δ x^T, ∂_b L = δ](https://latex.codecogs.com/gif.latex?%5Cpartial_WL%3D%5Cdelta%20x%5ET%2C%5C%3B%5Cpartial_bL%3D%5Cdelta)
