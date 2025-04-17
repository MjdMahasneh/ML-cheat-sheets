# Matrix Calculus Cheatsheet for Machine Learning

---

## 1. Vector Derivatives

**Linear Form:** ![d/dx (a^T x) = a](https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cpartial%7D%7B%5Cpartial%20x%7D%28a%5ET%5C,x%29%3Da)
Derivative of a constant vector–inner product.

- Example: ![d/dx ([1,2]·[x1,x2]) = [1,2]](https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cpartial%7D%7B%5Cpartial%20x%7D%28%5B1%2C2%5D%5ET%5C,%5Bx_1%2Cx_2%5D%29%3D%5B1%2C2%5D%5ET)

---

**Quadratic Form:** ![d/dx (x^T A x) = (A+A^T)x](https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cpartial%7D%7B%5Cpartial%20x%7D%28x%5ET%5C,A%5C,x%29%3D%28A%2BA%5ET%29%5C,x)
Applies for any square matrix \(A\).

- Example: if \(A=I\),
  ![d/dx (x^T x) = 2x](https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cpartial%7D%7B%5Cpartial%20x%7D%28x%5ET%5C,x%29%3D2x)

---

**Least‑Squares Loss:**  

![Least‑Squares Loss](https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cpartial%7D%7B%5Cpartial%5Cmathbf%7Bx%7D%7D%5C%7CA%5Cmathbf%7Bx%7D-b%5C%7C_2%5E2%3D2A%5ET%28A%5Cmathbf%7Bx%7D-b%29)
Common regression gradient.

Example: if \(A=I\),

![d/dx ||x–b||_2^2 = 2(x–b)](https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cpartial%7D%7B%5Cpartial%20x%7D%5C%7Cx-b%5C%7C_2%5E2%3D2%28x-b%29)

---

## 2. Matrix Derivatives

**Trace–Linear:** ![d/dX Tr(A X) = A^T](https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cpartial%7D%7B%5Cpartial%20X%7D%5Cmathrm%7BTr%7D%28A%5C,X%29%3DA%5ET)
Where \(A\) is constant.

- Example: ![d/dX Tr(A X) = A^T](https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cpartial%7D%7B%5Cpartial%20X%7D%5Cmathrm%7BTr%7D%28%5Cbegin%7Bbmatrix%7D1%262%5C%5C3%264%5Cend%7Bbmatrix%7DX%29%3D%5Cbegin%7Bbmatrix%7D1%263%5C%5C2%264%5Cend%7Bbmatrix%7D)

---

**Trace–Quadratic:** ![d/dX Tr(X^T A X B) = A X B^T + A^T X B](https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cpartial%7D%7B%5Cpartial%20X%7D%5Cmathrm%7BTr%7D%28X%5ET%5C,A%5C,X%5C,B%29%3DA%5C,X%5C,B%5ET%20%2B%20A%5ET%5C,X%5C,B)
For conforming constant matrices \(A,B\).

---

**Frobenius Norm:** ![d/dX ||X||_F^2 = 2X](https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cpartial%7D%7B%5Cpartial%20X%7D%5C%7CX%5C%7C_F%5E2%3D2%5C,X)

---

**Determinant:** ![d/dX det(X) = det(X) X^{-T}](https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cpartial%7D%7B%5Cpartial%20X%7D%5Cdet%28X%29%3D%5Cdet%28X%29%5C,X%5E%7B-T%7D)
For invertible \(X\).

---

**Log‑Det:** ![d/dX ln det(X) = X^{-T}](https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cpartial%7D%7B%5Cpartial%20X%7D%5Cln%5Cdet%28X%29%3DX%5E%7B-T%7D)

--- 

## 3. Useful Identities

- **Derivative of Inverse:**
  ![d/dX X^-1 = –X^-T ⊗ X^-1](https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cpartial%7D%7B%5Cpartial%20X%7DX%5E%7B-1%7D%3D-X%5E%7B-T%7D%5Cotimes%20X%5E%7B-1%7D)

- **Derivative of Trace Log:**
  ![d/dX Tr(ln X) = (X^-1)^T](https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cpartial%7D%7B%5Cpartial%20X%7D%5Cmathrm%7BTr%7D%28%5Cln%20X%29%3D%28X%5E%7B-1%7D%29%5ET)

---

## 4. Putting It Together

Use these to derive gradients for:

- **Ridge Regression:**  

  ![Ridge Regression](https://latex.codecogs.com/gif.latex?%5C%7CA%5C%2Cx-b%5C%7C%5E2%20%2B%20%5Clambda%5C%7Cx%5C%7C%5E2)

- **Matrix Factorization:**  

  ![Matrix Factorization](https://latex.codecogs.com/gif.latex?%5C%7CX%5C%2CY%5ET%20-%20M%5C%7C_F%5E2)

- **Gaussian Log‑Likelihood:**  

  ![Gaussian Log‑Likelihood](https://latex.codecogs.com/gif.latex?%5Cln%5Cdet%5CSigma%20%2B%20%28x-%5Cmu%29%5ET%5CSigma%5E%7B-1%7D%28x-%5Cmu%29)


Just apply the above rules term by term!
