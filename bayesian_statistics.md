# Bayesian Statistics Cheatsheet

---

## 1. Bayes’ Theorem

**Formula:**  

![P(A|B)=P(B|A)P(A)/P(B)](https://latex.codecogs.com/gif.latex?P%28A%7CB%29%3D%5Cfrac%7BP%28B%7CA%29P%28A%29%7D%7BP%28B%29%7D)

**Intuition:** update your belief  
![P(A)](https://latex.codecogs.com/gif.latex?P%28A%29) (prior) after observing data  
![B](https://latex.codecogs.com/gif.latex?B).

**Example:**  
    P(rain|wet)  
    = P(wet|rain) · P(rain) / P(wet)  
    = 0.9 · 0.2 / 0.3 ≈ 0.60

---

## 2. Components

- **Prior:**  
  ![P(θ)](https://latex.codecogs.com/gif.latex?P%28%5Ctheta%29)

- **Likelihood:**  
  ![P(D|θ)](https://latex.codecogs.com/gif.latex?P%28D%7C%5Ctheta%29)

- **Posterior:**  
  ![P(θ|D) ∝ P(D|θ)P(θ)](https://latex.codecogs.com/gif.latex?P%28%5Ctheta%7CD%29%5Cpropto%20P%28D%7C%5Ctheta%29P%28%5Ctheta%29)

- **Evidence:**  
  ![P(D)=∫P(D|θ)P(θ)dθ](https://latex.codecogs.com/gif.latex?P%28D%29%3D%5Cint%20P%28D%7C%5Ctheta%29P%28%5Ctheta%29d%5Ctheta)

---

## 3. Conjugate Priors

| Model           | Prior                                                  | Likelihood   | Posterior                                              |
| --------------- | ------------------------------------------------------ | ------------ | ------------------------------------------------------ |
| **Bernoulli**   | ![Beta(α,β)](https://latex.codecogs.com/gif.latex?Beta%28%5Calpha%2C%5Cbeta%29)      | Binomial     | ![Beta(α+k,β+n-k)](https://latex.codecogs.com/gif.latex?Beta%28%5Calpha%2Bk%2C%5Cbeta%2Bn-k%29) |
| **Gaussian**    | ![Normal(μ₀,σ₀²)](https://latex.codecogs.com/gif.latex?Normal%28%5Cmu_0%2C%5Csigma_0%5E2%29) | Gaussian     | Normal                                                 |
| **Multinomial** | ![Dirichlet(α₁…α_K)](https://latex.codecogs.com/gif.latex?Dirichlet%28%5Calpha_1%E2%80%A6%5Calpha_K%29) | Multinomial  | Dirichlet                                              |

**Example (Beta‑Binomial):**  
    Prior:     Beta(2,2)  
    Data:      8 heads, 4 tails  
    Posterior: Beta(2+8, 2+4) = Beta(10,6)

---

## 4. Point Estimates

- **MAP:**  
  ![θ̂_MAP = argmax P(θ|D)](https://latex.codecogs.com/gif.latex?%5Chat%5Ctheta_%7BMAP%7D%3D%5Carg%5Cmax_%7B%5Ctheta%7D%20P%28%5Ctheta%7CD%29)

- **MLE:**  
  ![θ̂_MLE = argmax P(D|θ)](https://latex.codecogs.com/gif.latex?%5Chat%5Ctheta_%7BMLE%7D%3D%5Carg%5Cmax_%7B%5Ctheta%7D%20P%28D%7C%5Ctheta%29)

*MAP* uses the prior; *MLE* does not.

---

## 5. Predictive Distribution

**Posterior Predictive:**  
![P(x_new|D)=∫P(x_new|θ)P(θ|D)dθ](https://latex.codecogs.com/gif.latex?P%28x_%7Bnew%7D%7CD%29%3D%5Cint%20P%28x_%7Bnew%7D%7C%5Ctheta%29P%28%5Ctheta%7CD%29d%5Ctheta)

**Example (Beta‑Binomial):**  
    ![P(head|D)=(α+k)/(α+β+n)](https://latex.codecogs.com/gif.latex?P%28%5Cmathrm%7Bhead%7D%7CD%29%3D%5Cfrac%7B%5Calpha%2Bk%7D%7B%5Calpha%2B%5Cbeta%2Bn%7D)

---

## 6. Model Comparison

- **Bayes Factor:**  
  ![BF₁₀ = P(D|M₁)/P(D|M₀)](https://latex.codecogs.com/gif.latex?BF_%7B10%7D%3D%5Cfrac%7BP%28D%7CM_1%29%7D%7BP%28D%7CM_0%29%7D)  
  > Ratio of evidences; >1 favors _M₁_.

---

## 7. Practical Tips

- **Choose Priors** to encode knowledge but remain flexible.  
- **Use MCMC** (e.g., Metropolis–Hastings, NUTS) when no closed‑form posterior.  
- **Check Convergence** with trace plots, _R̂_, and ESS.  
