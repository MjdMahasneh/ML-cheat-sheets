# Attention Mechanisms Cheatsheet

---

## 1. Scaled Dot‑Product Attention

**Formula:**  

![Attention(Q,K,V) = softmax(QKᵀ/√dₖ) V](https://latex.codecogs.com/gif.latex?%5Cmathrm%7BAttention%7D%28Q%2CK%2CV%29%3D%5Cmathrm%7Bsoftmax%7D%5CBigl%28%5Cfrac%7BQK%5ET%7D%7B%5Csqrt%7Bd_k%7D%7D%5CBigr%29V)

- **Q, K, V**: query, key, value matrices  
- **dₖ**: dimension of keys  
- Softmax over each query row.

**Example Shapes:**  
- Q: (T_q × dₖ), K: (Tₖ × dₖ), V: (Tₖ × d_v)  
- Output: (T_q × d_v)

---

## 2. Multi‑Head Attention

**Formula:**  

![MultiHead(Q,K,V) = Concat(head₁,…,headₕ) Wᴼ](https://latex.codecogs.com/gif.latex?%5Cmathrm%7BMultiHead%7D%28Q%2CK%2CV%29%3D%5Cmathrm%7BConcat%7D%28head_1%2C%5Cdots%2Chead_h%29W%5EO)

where each head:  

![headᵢ = Attention(QWᵢᵠ, KWᵢᵏ, VWᵢᵛ)](https://latex.codecogs.com/gif.latex?head_i%3D%5Cmathrm%7BAttention%7D%28QW_i%5EQ%2CKW_i%5EK%2CVW_i%5EV%29)

- **h**: number of heads  
- Projection matrices Wᵢᵠ, Wᵢᵏ, Wᵢᵛ, and Wᴼ.

---

## 3. Causal (Future) Masking

To prevent attending to future tokens:  

![mask(i,j)= {0 if j≤i; −∞ if j>i}](https://latex.codecogs.com/gif.latex?%5Cmathrm%7Bmask%7D%28i%2Cj%29%3D%5Cbegin%7Bcases%7D0%2C%26j%5Cle%20i%5C%5C-%5Cinfty%2C%26j%3Ei%5Cend%7Bcases%7D)

Add mask before softmax:  

![softmax((QKᵀ)/√dₖ + mask)](https://latex.codecogs.com/gif.latex?%5Cmathrm%7Bsoftmax%7D%5CBigl%28%5Cfrac%7BQK%5ET%7D%7B%5Csqrt%7Bd_k%7D%7D%2B%5Cmathrm%7Bmask%7D%5CBigr%29)

---

## 4. Positional Encoding

**Sinusoidal:**  

![PE₍pos,2i₎ = sin(pos/10000^{2i/dₘₒdₑₗ})](https://latex.codecogs.com/gif.latex?PE_%7Bpos%2C2i%7D%3D%5Csin%5C%21%5Cbigl%28%5Cfrac%7Bpos%7D%7B10000%5E%7B2i%2Fd_%7Bmodel%7D%7D%7D%5Cbigr%29)  
![PE₍pos,2i+1₎ = cos(pos/10000^{2i/dₘₒdₑₗ})](https://latex.codecogs.com/gif.latex?PE_%7Bpos%2C2i%2B1%7D%3D%5Ccos%5C%21%5Cbigl%28%5Cfrac%7Bpos%7D%7B10000%5E%7B2i%2Fd_%7Bmodel%7D%7D%7D%5Cbigr%29)

Encodes token position into continuous values.

---

## 5. Complexity

- **Time:** O(n²·d) for sequence length n and dimension d.  
- **Memory:** O(n²) for storing attention scores.

---

## 6. Implementation Tips

- **Efficient Batch:** use optimized matrix multiplication.  
- **Dropout:** apply after softmax on attention weights.  
- **Layer Norm:** add before/after attention sublayer.  
- **Residual Connection:** add input to output of attention.

---

## 7. Common Libraries

- **PyTorch:** `nn.MultiheadAttention`, `F.scaled_dot_product_attention`  
- **TensorFlow:** `tf.keras.layers.MultiHeadAttention`

---

## 8. References

- Vaswani et al., _Attention Is All You Need_  
- Illustrated Transformer blog posts (e.g., “The Annotated Transformer”)
