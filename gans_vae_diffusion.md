# GANs, VAEs & Diffusion Cheatsheet

---

## 1. GANs
- **Generator Loss:**  
  ![Generator Loss](https://latex.codecogs.com/gif.latex?%5Cmathcal%7BL%7D_G%3D%5Cmathbb%7BE%7D_%7Bz%5Csim%20p_z%7D%5B%5Clog%281-D%28G%28z%29%29%5D)

- **Discriminator Loss:**  
  ![Discriminator Loss](https://latex.codecogs.com/gif.latex?%5Cmathcal%7BL%7D_D%3D-%5Cmathbb%7BE%7D_%7Bx%7D%5B%5Clog%20D%28x%29%5D-%5Cmathbb%7BE%7D_%7Bz%7D%5B%5Clog%281-D%28G%28z%29%29%5D)

---

## 2. VAE
- **ELBO:**  
  ![ELBO](https://latex.codecogs.com/gif.latex?%5Cmathbb%7BE%7D_%7Bq%28z%7Cx%29%7D%5B%5Clog%20p%28x%7Cz%29%5D-%5Cmathrm%7BKL%7D%5Bq%28z%7Cx%29%5C%7Cp%28z%29%5D)

---

## 3. Diffusion Models
- **Forward (noising):**  
  ![xₜ = √αₜ xₜ₋₁ + √(1−αₜ) ε](https://latex.codecogs.com/gif.latex?x_t%3D%5Csqrt%7B%5Calpha_t%7Dx_%7Bt-1%7D%2B%5Csqrt%7B1-%5Calpha_t%7D%5C%2C%5Cepsilon)

- **Reverse (denoising):** learn a model to predict the noise ε and reconstruct xₜ₋₁ from xₜ.

---
