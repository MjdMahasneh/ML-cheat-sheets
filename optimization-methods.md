# Optimization Algorithms Cheatsheet

---

## 1. Stochastic Gradient Descent (SGD)

**Update:**  

![θₜ₊₁ = θₜ − α gₜ](https://latex.codecogs.com/gif.latex?%5Ctheta_%7Bt%2B1%7D%3D%5Ctheta_t-%5Calpha%20g_t)

- **α (Learning Rate):** step size.  
- **Intuition:** move opposite to gradient to minimize loss.  
- **Example:** α=0.1, g=2 → θ ← θ − 0.2

---

## 2. Momentum

**Update:**  

![vₜ = β vₜ₋₁ + (1−β) gₜ; θₜ₊₁ = θₜ − α vₜ](https://latex.codecogs.com/gif.latex?v_t%3D%5Cbeta%20v_%7Bt-1%7D%2B%281-%5Cbeta%29g_t%3B%20%5Ctheta_%7Bt%2B1%7D%3D%5Ctheta_t-%5Calpha%20v_t)

- **β (Momentum):** how much past gradients influence update.  
- **Intuition:** accelerates in consistent gradient directions, dampens oscillations.  
- **Example:** β=0.9, initial v=0, g=2 → v=0.2, θ ← θ − 0.02

---

## 3. Nesterov Accelerated Gradient (NAG)

**Lookahead:**  

![θ̃ = θₜ − α β vₜ₋₁](https://latex.codecogs.com/gif.latex?%5Ctilde%5Ctheta%3D%5Ctheta_t-%5Calpha%5Cbeta%20v_%7Bt-1%7D)

**Update:**  

![vₜ = β vₜ₋₁ + (1−β) ∇f(θ̃); θₜ₊₁ = θₜ − α vₜ](https://latex.codecogs.com/gif.latex?v_t%3D%5Cbeta%20v_%7Bt-1%7D%2B%281-%5Cbeta%29%5Cnabla%20f%28%5Ctilde%5Ctheta%29%3B%20%5Ctheta_%7Bt%2B1%7D%3D%5Ctheta_t-%5Calpha%20v_t)

- **Intuition:** compute gradient at an approximate next position for more responsive updates.

---

## 4. AdaGrad

**Update:**  

![AdaGrad update](https://latex.codecogs.com/gif.latex?G_t%3DG_%7Bt-1%7D%2Bg_t%5E2%3B%20%5Ctheta_%7Bt%2B1%7D%3D%5Ctheta_t-%5Cfrac%7B%5Calpha%7D%7B%5Csqrt%7BG_t%2B%5Cepsilon%7D%7D%20g_t)

- **Intuition:** larger learning rate for infrequent features; smaller for frequent.

---

## 5. RMSProp

**Update:**  

![RMSProp update](https://latex.codecogs.com/gif.latex?E%5Bg%5E2%5D_t%3D%5Crho%20E%5Bg%5E2%5D_%7Bt-1%7D%2B%281-%5Crho%29g_t%5E2%3B%20%5Ctheta_%7Bt%2B1%7D%3D%5Ctheta_t-%5Cfrac%7B%5Calpha%7D%7B%5Csqrt%7BE%5Bg%5E2%5D_t%2B%5Cepsilon%7D%7D%20g_t)

- **Intuition:** maintain moving average of squared gradients to normalize updates.

---

## 6. Adam

**Moments update:**  
![mₜ = β₁ mₜ₋₁ + (1−β₁) gₜ](https://latex.codecogs.com/gif.latex?m_t%3D%5Cbeta_1%20m_%7Bt-1%7D%2B%281-%5Cbeta_1%29%20g_t)  
![vₜ = β₂ vₜ₋₁ + (1−β₂) gₜ²](https://latex.codecogs.com/gif.latex?v_t%3D%5Cbeta_2%20v_%7Bt-1%7D%2B%281-%5Cbeta_2%29%20g_t%5E2)

**Bias correction:**  
![m̂ₜ = mₜ/(1−β₁ᵗ)](https://latex.codecogs.com/gif.latex?%5Chat%20m_t%3D%5Cfrac%7Bm_t%7D%7B1-%5Cbeta_1%5Et%7D)  
![v̂ₜ = vₜ/(1−β₂ᵗ)](https://latex.codecogs.com/gif.latex?%5Chat%20v_t%3D%5Cfrac%7Bv_t%7D%7B1-%5Cbeta_2%5Et%7D)

**Parameter update:**  
![θₜ₊₁ = θₜ − α (m̂ₜ/(√v̂ₜ + ε))](https://latex.codecogs.com/gif.latex?%5Ctheta_%7Bt%2B1%7D%3D%5Ctheta_t-%5Calpha%20%5Cfrac%7Bm_hat_t%7D%7B%5Csqrt%7Bv_hat_t%7D%2B%5Cepsilon%7D)

- **Intuition:** combines momentum and RMSProp for adaptive, resilient updates.  
- **Defaults:** β₁=0.9, β₂=0.999, ε=1e-8.  
