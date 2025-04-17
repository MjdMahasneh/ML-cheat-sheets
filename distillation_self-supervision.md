# Distillation & Self‑Supervision Cheatsheet

---

## 1. Knowledge Distillation

**Goal:** Transfer knowledge from a large, accurate **teacher** model to a smaller **student**.

**Loss:**  

![KD Loss](https://latex.codecogs.com/gif.latex?L%3D%5Calpha%5C%2CL_%7BCE%7D%28y%2Cp_s%29%2B%281-%5Calpha%29%5C%2CT%5E2%5C%2C%5Cmathrm%7BKL%7D%5Cbigl%28%5Cmathrm%7Bsoftmax%7D%28z_t%2FT%29%5C%2C%7C%7C%5C%2C%5Cmathrm%7Bsoftmax%7D%28z_s%2FT%29%5Cbigr%29)

- **α:** balance between true-label loss and distillation loss.  
- **T (Temperature):** softens probabilities, revealing dark knowledge.

**Example:**
- Teacher logits: [2.0, 0.5] → softmax at T=2: [0.69, 0.31]  
- Student trains to match these softened distributions.

---

## 2. Contrastive Self‑Supervision

**Goal:** Learn representations by pulling similar (positive) pairs together and pushing dissimilar (negative) pairs apart.

**InfoNCE Loss:**  

![InfoNCE Loss](https://latex.codecogs.com/gif.latex?L%3D-%5Clog%5Cfrac%7B%5Cexp%28%5Cmathrm%7Bsim%7D%28h_i%2Ch_j%29%2F%5Ctau%29%7D%7B%5Csum_k%5Cexp%28%5Cmathrm%7Bsim%7D%28h_i%2Ch_k%29%2F%5Ctau%29%7D)

- **sim:** e.g., cosine similarity.  
- **τ:** temperature hyperparameter.

**Example (SimCLR):**
1. Augment image twice → two views (positive).  
2. All other images in batch as negatives.  
3. Train encoder so positive pair embeddings align.

---

## 3. Weak Supervision (Brief)

**Goal:** Use noisy heuristics or labeling functions to generate weak labels.  
- Aggregate via label model (e.g., Snorkel) to estimate true labels.
