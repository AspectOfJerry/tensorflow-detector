# tensorflow-detector

## [MobileNet](https://arxiv.org/pdf/1704.04861.pdf) body architecture

- Type: Type of layer or operation in the neural network.
- Stride: Step size of the convolutional kernel.
- Kernel (Filter) Shape: Dimensions of the convolutional kernel.
- Input Shape: Dimensions of the input tensor.

- dw: Depthwise convolutional layer.
- s: Stride.
- AvgPool: Average pooling layer.
- FC: Fully connected layer.
- Softmax: Softmax layer.

|      # |  Type \| Stride   | Kernel Shape  | Input Shape |
|-------:|:-----------------:|:-------------:|:-----------:|
|  **1** |   Conv2D \| s2    |   3x3x3x32    |  224x224x3  |
|  **2** |  Conv2D dw \| s1  |   3x3x32 dw   | 112x112x32  |
|      3 |   Conv2D \| s1    |   1x1x32x64   | 112x112x32  |
|      4 |  Conv2D dw \| s2  |   3x3x64 dw   | 112x112x64  |
|  **5** |   Conv2D \| s1    |  1x1x64x128   |  56x56x64   |
|  **6** |  Conv2D dw \| s1  |  3x3x128 dw   |  56x56x128  |
|      7 |   Conv2D \| s1    |  1x1x128x128  |  56x56x128  |
|      8 |  Conv2D dw \| s2  |  3x3x128 dw   |  56x56x128  |
|  **9** |   Conv2D \| s1    |  1x1x128x256  |  28x28x128  |
| **10** |  Conv2D dw \| s1  |  3x3x256 dw   |  28x28x256  |
|     11 |   Conv2D \| s1    |  1x1x256x256  |  28x28x256  |
|     12 |  Conv2D dw \| s2  |  3x3x256 dw   |  28x28x256  |
| **13** |   Conv2D \| s1    |  1x1x256x512  |  14x14x256  |
| **14** |  Conv2D dw \| s1  |  3x3x512 dw   |  14x14x512  |
|     15 |   Conv2D \| s1    |  1x1x512x512  |  14x14x512  |
|     16 |  Conv2D dw \| s1  |  3x3x512 dw   |  14x14x512  |
|     17 |   Conv2D \| s1    |  1x1x512x512  |  14x14x512  |
|     18 |  Conv2D dw \| s1  |  3x3x512 dw   |  14x14x512  |
|     19 |   Conv2D \| s1    |  1x1x512x512  |  14x14x512  |
|     20 |  Conv2D dw \| s1  |  3x3x512 dw   |  14x14x512  |
|     21 |   Conv2D \| s1    |  1x1x512x512  |  14x14x512  |
|     22 |  Conv2D dw \| s1  |  3x3x512 dw   |  14x14x512  |
|     23 |   Conv2D \| s1    |  1x1x512x512  |  14x14x512  |
|     24 |  Conv2D dw \| s2  |  3x3x512 dw   |  14x14x512  |
| **25** |   Conv2D \| s1    | 1x1x512x1024  |   7x7x512   |
| **26** |  Conv2D dw \| s1  |  3x3x1024 dw  |  7x7x1024   |
|     27 |   Conv2D \| s1    | 1x1x1024x1024 |  7x7x1024   |
|     28 |  Conv2D dw \| s1  |  3x3x1024 dw  |  7x7x1024   |
|     29 | Conv2D \| s1 (x2) | 1x1x1024x1001 |  7x7x1024   |
|     30 |   AvgPool \| s1   |  7x7x1024 dw  |  7x7x1024   |
| **31** |     FC \| s1      | 1x1x1024x1001 |  1x1x1024   |
| **32** |   Softmax \| s1   |  Classifier   |  1x1x1001   |