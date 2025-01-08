---
title: Python - Numpy notes
date: '2020-06-18'
slug: python-numpy-notes
categories:
  - Dev
tags:
  - numpy
  - python
draft: false
summary: " "
---


### Einsum

+ Normal matrix-matrix multiplication:

```py
A = rnd(8)
B = rnd(10, 8) 
# make sure shape-compatible
np.matmul(A, B.T) # (10, )
np.matmul(B, A) # (10, )
```

+ When working with batch, say size `N`:

```python {hl_lines=[4]}
A = rnd(N, 8)
B = rnd(N, 10, 8)
A = A.reshape(N, 1, 8)
B = B.transpose(0, 2, 1) # (N, 8, 10)
np.matmul(A, B) # (N, 1, 10)
```

+ More convenient and efficient:

```python
np.einsum("nd,nmd->nm", A, B)
```

+ More [detail](https://ajcr.net/Basic-guide-to-einsum/)
