# Probability and Distributions Cheatsheet

## Probability Computing Rules 

---

## 1. Complement Rule
**Complement:**  
![P(A^c)=1-P(A)](https://latex.codecogs.com/gif.latex?P%28A%5Ec%29%3D1-P%28A%29)

---

## 2. Addition Rule
**General Addition:**  
![P(A ∪ B)=P(A)+P(B)-P(A ∩ B)](https://latex.codecogs.com/gif.latex?P%28A%5Ccup%20B%29%3DP%28A%29%2BP%28B%29-P%28A%5Ccap%20B%29)

**Mutually Exclusive:**  
![P(A ∪ B)=P(A)+P(B)](https://latex.codecogs.com/gif.latex?P%28A%5Ccup%20B%29%3DP%28A%29%2BP%28B%29)

---

## 3. Multiplication Rule
**General Multiplication:**  
![P(A ∩ B)=P(A) P(B|A)](https://latex.codecogs.com/gif.latex?P%28A%5Ccap%20B%29%3DP%28A%29%5C,%20P%28B%7CA%29)

**Independent Events:**  
![P(A ∩ B)=P(A) P(B)](https://latex.codecogs.com/gif.latex?P%28A%5Ccap%20B%29%3DP%28A%29%5C,%20P%28B%29)

---

## 4. Conditional Probability
**Definition:**  
![P(A|B)=P(A ∩ B)/P(B)](https://latex.codecogs.com/gif.latex?P%28A%7CB%29%3D%5Cfrac%7BP%28A%5Ccap%20B%29%7D%7BP%28B%29%7D)

---

## 5. Total Probability Theorem
**Law of Total Probability:**  
![P(A)=Σ P(A|B_i) P(B_i)](https://latex.codecogs.com/gif.latex?P%28A%29%3D%5Csum_iP%28A%7CB_i%29%5C%2CP%28B_i%29)

---

## 6. Bayes’ Theorem
**Bayes’ Rule:**  
![P(B_j|A)=P(A|B_j)P(B_j)/Σ P(A|B_i)P(B_i)](https://latex.codecogs.com/gif.latex?P%28B_j%7CA%29%3D%5Cfrac%7BP%28A%7CB_j%29P%28B_j%29%7D%7B%5Csum_iP%28A%7CB_i%29P%28B_i%29%7D)

---

## 7. Inclusion–Exclusion (Three Events)
**Three-Event Inclusion–Exclusion:**  
![P(A ∪ B ∪ C)=P(A)+P(B)+P(C)-P(A∩B)-P(A∩C)-P(B∩C)+P(A∩B∩C)](https://latex.codecogs.com/gif.latex?P%28A%5Ccup%20B%5Ccup%20C%29%3DP%28A%29%2BP%28B%29%2BP%28C%29-P%28A%5Ccap%20B%29-P%28A%5Ccap%20C%29-P%28B%5Ccap%20C%29%2BP%28A%5Ccap%20B%5Ccap%20C%29)

---

## Distributions 

---

## 1. Discrete Distributions

**Bernoulli:**  
![P(X=x)=p^x(1-p)^{1-x}](https://latex.codecogs.com/gif.latex?%5CPr%28X%3Dx%29%3Dp%5Ex%281-p%29%5E%7B1-x%7D)  
- Example:  
  ![P(X=1)=p, P(X=0)=1-p](https://latex.codecogs.com/gif.latex?%5CPr%28X%3D1%29%3Dp%2C%5C%3B%5CPr%28X%3D0%29%3D1-p)

---

**Binomial:**  
![P(X=k)=C(n,k)p^k(1-p)^{n-k}](https://latex.codecogs.com/gif.latex?%5CPr%28X%3Dk%29%3D%5Cbinom%7Bn%7D%7Bk%7Dp%5Ek%281-p%29%5E%7Bn-k%7D)  
- Example:  
  ![P(X=2)=C(5,2)(0.4)^2(0.6)^3](https://latex.codecogs.com/gif.latex?%5CPr%28X%3D2%29%3D%5Cbinom%7B5%7D%7B2%7D%280.4%29%5E2%280.6%29%5E3)

---

**Poisson:**  
![P(X=k)=e^{-λ}λ^k/k!](https://latex.codecogs.com/gif.latex?%5CPr%28X%3Dk%29%3D%5Cfrac%7Be%5E%7B-%5Clambda%7D%5Clambda%5Ek%7D%7Bk%21%7D)  
- Example:  
  ![P(X=2)=e^{-3}3^2/2!](https://latex.codecogs.com/gif.latex?%5CPr%28X%3D2%29%3De%5E%7B-3%7D%5Cfrac%7B3%5E2%7D%7B2%21%7D)

---

**Categorical:**  
![P(X=i)=p_i](https://latex.codecogs.com/gif.latex?%5CPr%28X%3Di%29%3Dp_i)  
- Example:  
  ![P(X=2)=0.5, p=[0.2,0.5,0.3]](https://latex.codecogs.com/gif.latex?%5CPr%28X%3D2%29%3D0.5%5Cquad%28p%3D%5B0.2%2C0.5%2C0.3%5D%29)

---

## 2. Continuous Distributions

**Uniform (U(a,b)):**  
![f(x)=1/(b-a)](https://latex.codecogs.com/gif.latex?f%28x%29%3D%5Cfrac%7B1%7D%7Bb-a%7D)  
- Example:  
  ![f(x)=1 for a=0,b=1](https://latex.codecogs.com/gif.latex?f%28x%29%3D1%5Cquad%28a%3D0%2Cb%3D1%29)

---

**Normal (N(μ,σ²)):**  
![f(x)=1/√(2πσ²)e^{-(x-μ)²/(2σ²)}](https://latex.codecogs.com/gif.latex?f%28x%29%3D%5Cfrac%7B1%7D%7B%5Csqrt%7B2%5Cpi%5Csigma%5E2%7D%7De%5E%7B-%5Cfrac%7B%28x-%5Cmu%29%5E2%7D%7B2%5Csigma%5E2%7D%7D)  
- Example:  
  ![f(0)=1/sqrt(2π) for N(0,1)](https://latex.codecogs.com/gif.latex?f%280%29%3D%5Cfrac%7B1%7D%7B%5Csqrt%7B2%5Cpi%7D%7D%5Cquad%28%5Cmu%3D0%2C%5Csigma%5E2%3D1%29)

---

**Exponential:**  
![f(x)=λ e^{-λ x}](https://latex.codecogs.com/gif.latex?f%28x%29%3D%5Clambda%20e%5E%7B-%5Clambda%20x%7D)  
- Example:  
  ![f(0.5)=2 e^{-1}](https://latex.codecogs.com/gif.latex?f%280.5%29%3D2e%5E%7B-1%7D%5Cquad%28%5Clambda%3D2%29)

---

## 3. Expectations & Variance

**Expectation (discrete):**  
![E[X]=Σ x P(X=x)](https://latex.codecogs.com/gif.latex?E%5BX%5D%3D%5Csum_x%20x%5C%2C%5CPr%28X%3Dx%29)  
**Expectation (continuous):**  
![E[X]=∫ x f(x) dx](https://latex.codecogs.com/gif.latex?E%5BX%5D%3D%5Cint_%7B-%5Cinfty%7D%5E%7B%5Cinfty%7Dx%5C%2Cf%28x%29%5C%2Cdx)

---

**Variance:**  
![Var(X)=E[(X-E[X])^2]](https://latex.codecogs.com/gif.latex?Var%28X%29%3DE%5B%28X-E%5BX%5D%29%5E2%5D)  
**Also:** Var(X)=E[X²]−(E[X])²
