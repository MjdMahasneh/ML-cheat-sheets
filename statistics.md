# Statistics Cheatsheet

---

## 1. Descriptive Statistics
- **Mean:**  
  ![μ = (1/N) ∑_{i=1}^N x_i](https://latex.codecogs.com/gif.latex?%5Cmu%20%3D%20%5Cfrac%7B1%7D%7BN%7D%5Csum_%7Bi%3D1%7D%5EN%20x_i)
- **Median:** middle value of sorted data
- **Variance:**  
  ![σ² = (1/N) ∑_{i=1}^N (x_i - μ)²](https://latex.codecogs.com/gif.latex?%5Csigma%5E2%20%3D%20%5Cfrac%7B1%7D%7BN%7D%5Csum_%7Bi%3D1%7D%5EN%20%28x_i%20-%20%5Cmu%29%5E2)
- **Standard Deviation:**  
  ![σ = √(σ²)](https://latex.codecogs.com/gif.latex?%5Csigma%20%3D%20%5Csqrt%7B%5Csigma%5E2%7D)

---

## 2. Correlation & Covariance
- **Covariance:**  
  ![Cov(X,Y) = (1/N) ∑ (x_i - μ_X)(y_i - μ_Y)](https://latex.codecogs.com/gif.latex?%5Cmathrm%7BCov%7D%28X%2CY%29%3D%5Cfrac%7B1%7D%7BN%7D%5Csum_%7Bi%3D1%7D%5EN%20%28x_i-%5Cmu_X%29%28y_i-%5Cmu_Y%29)
- **Pearson Correlation:**  
  ![ρ = Cov(X,Y)/(σ_X σ_Y)](https://latex.codecogs.com/gif.latex?%5Crho%20%3D%20%5Cfrac%7B%5Cmathrm%7BCov%7D%28X%2CY%29%7D%7B%5Csigma_X%20%5Csigma_Y%7D)

---

## 3. Sampling & CLT
- **Central Limit Theorem:** sample mean ~ N(μ, σ²/N)
- **Standard Error:**  
  ![SE = σ/√N](https://latex.codecogs.com/gif.latex?SE%20%3D%20%5Cfrac%7B%5Csigma%7D%7B%5Csqrt%7BN%7D%7D)

---

## 4. Confidence Interval (Mean)
- **CI:**  
  ![μ ± z_{α/2} σ/√N](https://latex.codecogs.com/gif.latex?%5Cmu%20%5Cpm%20z_%7B%5Calpha%2F2%7D%20%5Cfrac%7B%5Csigma%7D%7B%5Csqrt%7BN%7D%7D)

---

## 5. Hypothesis Testing
- **Z-test statistic:**  
  ![z = (x̄ - μ₀)/(σ/√N)](https://latex.codecogs.com/gif.latex?z%20%3D%20%5Cfrac%7B%5Cbar%7Bx%7D-%5Cmu_0%7D%7B%5Csigma%2F%5Csqrt%7BN%7D%7D)
- **p-value:** tail probability under null.
