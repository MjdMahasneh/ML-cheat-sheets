# RNNs, GRUs & Time Series Cheatsheet

---

## 1. Vanilla RNN Cell

![hₜ = tanh(Wₓ xₜ + Wₕ hₜ₋₁ + b)](https://latex.codecogs.com/gif.latex?h_t%3D%5Ctanh%28W_x%20x_t%2BW_h%20h_%7Bt-1%7D%2Bb%29)

---

## 2. GRU Cell

- **Update Gate:**  
  ![zₜ = σ(W_z xₜ + U_z hₜ₋₁)](https://latex.codecogs.com/gif.latex?z_t%3D%5Csigma%28W_z%20x_t%2BU_z%20h_%7Bt-1%7D%29)

- **Reset Gate:**  
  ![rₜ = σ(W_r xₜ + U_r hₜ₋₁)](https://latex.codecogs.com/gif.latex?r_t%3D%5Csigma%28W_r%20x_t%2BU_r%20h_%7Bt-1%7D%29)

- **Candidate:**  
  ![ĥₜ = tanh(Wₕ xₜ + Uₕ (rₜ ⊙ hₜ₋₁))](https://latex.codecogs.com/gif.latex?%5Ctilde%7Bh%7D_t%3D%5Ctanh%28W_h%20x_t%2BU_h%28r_t%5Codot%20h_%7Bt-1%7D%29%29)

- **Final State:**  
  ![hₜ = (1−zₜ) ⊙ hₜ₋₁ + zₜ ⊙ ĥₜ](https://latex.codecogs.com/gif.latex?h_t%3D%281-z_t%29%5Codot%20h_%7Bt-1%7D%2Bz_t%5Codot%5Ctilde%7Bh%7D_t)

---

## 3. Time Series Forecasting

- **Sliding Window:** use past N steps to predict the next.  
- **Evaluation Metrics:** MAE, RMSE, MAPE.
