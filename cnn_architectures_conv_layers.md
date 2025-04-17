# CNN Architectures & Convolution Layers Cheatsheet

---

## 1. Classic CNNs

### LeNet-5
- **Year:** 1998  
- **Structure:** 2 conv layers + 3 FC layers  
- **Use Case:** digit recognition (MNIST)

### AlexNet
- **Year:** 2012  
- **Features:** ReLU activations, dropout, data augmentation  
- **Structure:** 5 conv layers, 3 FC layers

### VGG (VGG16/19)
- **Year:** 2014  
- **Features:** homogeneous 3×3 conv stacks  
- **Structure:** 16 or 19 layers, very deep

---

## 2. Modern Architectures

### ResNet (Residual Network)
- **Year:** 2015  
- **Key Idea:** skip connections (identity shortcuts)  
- **Block:**  
  <img src="https://latex.codecogs.com/png.latex?y=\mathcal{F}(x)+x" alt="y=F(x)+x" />  
- **Depths:** 34, 50, 101, 152 layers

### Inception (GoogLeNet)
- **Year:** 2014  
- **Key Idea:** multi-branch conv filters (1×1, 3×3, 5×5)  
- **Inception Module:** concatenates multiple filter outputs

### DenseNet
- **Year:** 2017  
- **Key Idea:** dense connections, each layer receives all previous feature maps  
- **Block:**  
  <img src="https://latex.codecogs.com/png.latex?x_l=[x_0,x_1,...,x_{l-1}]" alt="x_l = concat of all previous x" />

### EfficientNet
- **Year:** 2019  
- **Key Idea:** compound scaling of depth, width, resolution  
- **Variants:** B0 to B7

### MobileNet
- **Year:** 2017  
- **Key Idea:** depthwise separable conv (DW conv + pointwise conv)  
- **Block:**  
  ```text
  Y = Conv1x1( ReLU( DWConv3x3(X) ) )
  ```

### ConvNeXt
- **Year:** 2022  
- **Key Idea:** modernized ResNet with larger kernels, inverted bottlenecks, LayerNorm  
- **Block:**  
  ```text
  X -> DWConv7x7 -> LN -> 1×1 conv -> GELU -> 1×1 conv -> + X
  ```

### RegNet
- **Year:** 2020  
- **Key Idea:** simple network design space, parameterized widths and depths

---

## 3. Convolution Variants

- **Standard Conv:** k×k filter over all channels  
- **Depthwise Separable Conv:** per-channel conv + 1×1 pointwise conv  
- **Group Conv:** channels split into G groups, conv per group  
- **Pointwise Conv:** 1×1 conv, used for channel mixing  
- **Dilated (Atrous) Conv:** k×k conv with gaps, expands receptive field  
- **Transposed Conv:** upsampling via learned filters (deconvolution)  
- **Deformable Conv:** learnable offsets to sampling locations  
- **Bottleneck Block:** reduce and restore channels with 1×1 convs  
- **Squeeze‑and‑Excitation (SE):** channel-wise attention via global pooling

---

## 4. Use Cases & Intuition

- **Skip Connections (ResNet):** mitigate vanishing gradient, ease training of deep nets.  
- **Separable Convs (MobileNet):** reduce computation and parameters for mobile deployment.  
- **Dense Connections (DenseNet):** encourage feature reuse, improve gradient flow.  
- **Compound Scaling (EfficientNet):** balance network dimensions for efficiency.

---
