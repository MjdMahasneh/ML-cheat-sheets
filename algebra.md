# Algebra Cheatsheet for Computer Vision

---

## 1. Basic Algebra

### 1.1 Notation
- **Scalars**: single values, lowercase (e.g., a, b).
- **Vectors**: bold lowercase, shape m×1 or 1×n (e.g., **v**, **u**).
- **Matrices**: bold uppercase, shape m×n (e.g., **A**, **B**).

### 1.2 Operations

- **Addition** ( ![m×n + m×n = m×n](https://latex.codecogs.com/gif.latex?m%5Ctimes%20n%20%2B%20m%5Ctimes%20n%20%3D%20m%5Ctimes%20n) ):
  ![Matrix Addition](https://latex.codecogs.com/gif.latex?%5Cbegin%7Bbmatrix%7D1%262%5C%5C3%264%5Cend%7Bbmatrix%7D%2B%5Cbegin%7Bbmatrix%7D5%266%5C%5C7%268%5Cend%7Bbmatrix%7D%3D%5Cbegin%7Bbmatrix%7D6%268%5C%5C10%2612%5Cend%7Bbmatrix%7D)

- **Scalar Multiplication** ( ![c × m×n = m×n](https://latex.codecogs.com/gif.latex?c%20%5Ctimes%20m%5Ctimes%20n%20%3D%20m%5Ctimes%20n) ):
  ![Scalar Multiplication](https://latex.codecogs.com/gif.latex?2%20%5Ctimes%20%5Cbegin%7Bbmatrix%7D1%20%26%202%5C%5C3%20%26%204%5Cend%7Bbmatrix%7D%20%3D%20%5Cbegin%7Bbmatrix%7D2%20%26%204%5C%5C6%20%26%208%5Cend%7Bbmatrix%7D)

- **Dot Product** ( ![1×n · n×1 = scalar](https://latex.codecogs.com/gif.latex?1%5Ctimes%20n%20%5Ccdot%20n%5Ctimes%201%20%3D%20scalar) ):
  ![Dot Product](https://latex.codecogs.com/gif.latex?%5Cbegin%7Bbmatrix%7D1%20%26%202%20%26%203%5Cend%7Bbmatrix%7D%20%5Cbegin%7Bbmatrix%7D4%5C%5C5%5C%5C6%5Cend%7Bbmatrix%7D%20%3D%2032)

- **Matrix Multiplication** ( ![m×k × k×n = m×n](https://latex.codecogs.com/gif.latex?m%5Ctimes%20k%20%5Ctimes%20k%5Ctimes%20n%20%3D%20m%5Ctimes%20n) ):
  ![Matrix Multiplication](https://latex.codecogs.com/gif.latex?%5Cbegin%7Bbmatrix%7D1%20%26%202%20%26%203%5C%5C4%20%26%205%20%26%206%5Cend%7Bbmatrix%7D%20%5Ctimes%20%5Cbegin%7Bbmatrix%7D7%20%26%208%5C%5C9%20%26%2010%5C%5C11%20%26%2012%5Cend%7Bbmatrix%7D%20%3D%20%5Cbegin%7Bbmatrix%7D58%20%26%2064%5C%5C139%20%26%20154%5Cend%7Bbmatrix%7D)

---

## 2. Linear Algebra

### 2.1 Vectors
- **Norm**: ![∥v∥₂=√∑iv²_i](https://latex.codecogs.com/gif.latex?%5C%7Cv%5C%7C_2%3D%5Csqrt%7B%5Csum_i%20v_i%5E2%7D)
- **Unit Vector**: ![v̂=v/∥v∥₂](https://latex.codecogs.com/gif.latex?%5Chat%7Bv%7D%3Dv%2F%5C%7Cv%5C%7C_2)

### 2.2 Matrices
- **Transpose**: ![A^T](https://latex.codecogs.com/gif.latex?A%5ET) flips rows↔columns.
- **Determinant**: ![det(A)](https://latex.codecogs.com/gif.latex?%5Cdet%28A%29) scales volume.
- **Inverse**: ![A^(-1)](https://latex.codecogs.com/gif.latex?A%5E%7B-1%7D) such that ![AA^(-1)=I](https://latex.codecogs.com/gif.latex?AA%5E%7B-1%7D%3DI).

### 2.3 Eigen Decomposition
- ![Av=λv](https://latex.codecogs.com/gif.latex?Av%3D%5Clambda%20v)
- ![A=VΛV^(-1)](https://latex.codecogs.com/gif.latex?A%3DV%5CLambda%20V%5E%7B-1%7D)

---

## 3. Matrix Decompositions

### 3.1 Singular Value Decomposition (SVD)
![A=UΣV^T](https://latex.codecogs.com/gif.latex?A%3DU%5CSigma%20V%5ET)

### 3.2 Eigenvalue Decomposition
![A=VΛV^(-1)](https://latex.codecogs.com/gif.latex?A%3DV%5CLambda%20V%5E%7B-1%7D)

---

## 4. Vector Spaces
- **Basis**: independent vectors spanning the space.
- **Dimension**: number of basis vectors.
- **Column Space**: span of columns of ![A](https://latex.codecogs.com/gif.latex?A).
- **Null Space**: solutions to ![Ax=0](https://latex.codecogs.com/gif.latex?Ax%3D0).

---

## 5. Optimization

### 5.1 Gradient Descent
![x_(k+1)=x_k−α∇f(x_k)](https://latex.codecogs.com/gif.latex?x_%7Bk%2B1%7D%3Dx_k-%5Calpha%5Cnabla%20f%28x_k%29)

### 5.2 Least Squares
![x=(A^TA)^(-1)A^Tb](https://latex.codecogs.com/gif.latex?x%3D%28A%5ETA%29%5E%7B-1%7DA%5ETb)

---

## 6. Probability & Statistics

### 6.1 Expectation & Variance
- ![E[X]=∑x xP(X=x)](https://latex.codecogs.com/gif.latex?E%5BX%5D%3D%5Csum_x%20xP%28X%3Dx%29)
- ![Var(X)=E[(X−E[X])²]](https://latex.codecogs.com/gif.latex?%5Cmathrm%7BVar%7D%28X%29%3DE%5B%28X-E%5BX%5D%29%5E2%5D)

### 6.2 Gaussian PDF
![f(x)=1/√(2πσ²)e^(-(x−μ)²/(2σ²))](https://latex.codecogs.com/gif.latex?f%28x%29%3D%5Cfrac%7B1%7D%7B%5Csqrt%7B2%5Cpi%5Csigma%5E2%7D%7De%5E%7B-%5Cfrac%7B%28x-%5Cmu%29%5E2%7D%7B2%5Csigma%5E2%7D%7D)

---

## 7. Useful Identities
- **Matrix Inversion Lemma**:
  ![(A+BCD)^(-1)=A^(-1)−A^(-1)B(C^(-1)+DA^(-1)B)^(-1)DA^(-1)](https://latex.codecogs.com/gif.latex?%28A%2BBCD%29%5E%7B-1%7D%3DA%5E%7B-1%7D-A%5E%7B-1%7DB%28C%5E%7B-1%7D%2BDA%5E%7B-1%7DB%29%5E%7B-1%7DDA%5E%7B-1%7D)
- **Trace & Determinant**:
  ![tr(A+B)=tr(A)+tr(B)](https://latex.codecogs.com/gif.latex?%5Cmathrm%7Btr%7D%28A%2BB%29%3D%5Cmathrm%7Btr%7D%28A%29%2B%5Cmathrm%7Btr%7D%28B%29),
  ![det(AB)=det(A)det(B)](https://latex.codecogs.com/gif.latex?%5Cdet%28AB%29%3D%5Cdet%28A%29%5Cdet%28B%29)

---

## 8. Computer Vision Specific

### 8.1 Homogeneous Coordinates
- Point: ![x=[u,v,1]^T](https://latex.codecogs.com/gif.latex?x%3D%5B%5Cbegin%7Bsmallmatrix%7Du%5C%5Cv%5C%5C1%5Cend%7Bsmallmatrix%7D%5D)
- Transform: ![x′=Hx](https://latex.codecogs.com/gif.latex?x%27%3DHx), ![H](https://latex.codecogs.com/gif.latex?H) is 3×3 homography.

### 8.2 Camera Calibration
![K=⎝⎛f_x0c_x001⎠⎞](https://latex.codecogs.com/gif.latex?K%3D%5Cbegin%7Bbmatrix%7Df_x%260%26c_x%5C%5C0%26f_y%26c_y%5C%5C0%260%261%5Cend%7Bbmatrix%7D)

### 8.3 Epipolar Geometry
- Fundamental matrix ![F](https://latex.codecogs.com/gif.latex?F): ![x′^TFx=0](https://latex.codecogs.com/gif.latex?x%27%5ETFx%3D0)

---

## 9. Resources
- **Books**: Strang – *Linear Algebra and Its Applications*; Szeliski – *Computer Vision: Algorithms & Applications*
- **Courses**: MIT OCW Linear Algebra; Udacity Computer Vision (Georgia Tech)
