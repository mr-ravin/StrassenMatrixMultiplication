# Strassen Matrix Multiplication
### for N x N matrices in C programming language

This repository includes source code for strasssen matrix multiplication in C programming language for n x n matrices.

#### Code Developer: [Ravin Kumar](https://mr-ravin.github.io) 

NOTE: this textual description of Strassen Matrix Multiplication is taken from [wikipedia](https://en.wikipedia.org/wiki/Strassen_algorithm)



Let A, B be two square matrices over a ring R. We want to calculate the matrix product C as

![](https://wikimedia.org/api/rest_v1/media/math/render/svg/96e48054fc368d460367e1f541a131ea4baedb99)

If the matrices A, B are not of type 2n × 2n we fill the missing rows and columns with zeros.

We partition A, B and C into equally sized block matrices

![](https://wikimedia.org/api/rest_v1/media/math/render/svg/41c6337190684aff7b69f124226d6e62d79ebca5)

with

![](https://wikimedia.org/api/rest_v1/media/math/render/svg/480fbf677c5973cedb5218c69501a41e1b325a1a)

then

![](https://wikimedia.org/api/rest_v1/media/math/render/svg/a08bea24eec9422cda82e6e04af1d96fc6822038)

With this construction we have not reduced the number of multiplications. We still need 8 multiplications to calculate the Ci,j matrices, the same number of multiplications we need when using standard matrix multiplication.

Now comes the important part. We define new matrices

![](https://wikimedia.org/api/rest_v1/media/math/render/svg/c12df2bb70f8f09f33f1ca4b8c2d577d5850a2ee)

only using 7 multiplications (one for each Mk) instead of 8. We may now express the C i,j in terms of M k, like this:

![](https://wikimedia.org/api/rest_v1/media/math/render/svg/e71779a8ecc64f3e1268485cf389a05cdd3e6bf8)

We iterate this division process n times (recursively) until the submatrices degenerate into numbers (elements of the ring R). The resulting product will be padded with zeroes just like A and B, and should be stripped of the corresponding rows and columns.

```python
Copyright (c) 2015 Ravin Kumar
Website: https://mr-ravin.github.io

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation 
files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, 
modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the 
Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the 
Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE 
WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR 
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, 
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```
