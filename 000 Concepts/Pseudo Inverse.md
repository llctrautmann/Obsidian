---
title: Pseudo Inverse
date:
  - 17-06-2024
time: 11:20
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
🍙: いや
type: 
formula: $\mathbf{A} \mathbf{A}^{\dagger} \mathbf{A}=\mathbf{A}, \mathbf{A}^{\dagger} \mathbf{A} \mathbf{A}^{\dagger}=\mathbf{A}^{\dagger},\left(\mathbf{A} \mathbf{A}^{\dagger}\right)^{\top}=\mathbf{A} \mathbf{A}^{\dagger},\left(\mathbf{A}^{\dagger} \mathbf{A}\right)^{\top}=\mathbf{A}^{\dagger} \mathbf{A}$
aliases: 
modified: 2024-06-17
---
# Pseudo Inverse
The Moore-Penrose pseudo-inverse of $\mathbf{A}$, pseudo inverse denoted $\mathbf{A}^{\dagger}$, is defined as the unique matrix that satisfies the following 4 properties:

$$\large\tag{1}
\mathbf{A} \mathbf{A}^{\dagger} \mathbf{A}=\mathbf{A}, \mathbf{A}^{\dagger} \mathbf{A} \mathbf{A}^{\dagger}=\mathbf{A}^{\dagger},\left(\mathbf{A} \mathbf{A}^{\dagger}\right)^{\top}=\mathbf{A} \mathbf{A}^{\dagger},\left(\mathbf{A}^{\dagger} \mathbf{A}\right)^{\top}=\mathbf{A}^{\dagger} \mathbf{A}
$$

If $\mathbf{A}$ is square and non-singular, then $\mathbf{A}^{\dagger}=\mathbf{A}^{-1}$.
If $m>n$ (tall, skinny) and the columns of $\mathbf{A}$ are linearly independent (so $\mathbf{A}$ is full rank), then

$$\large\tag{2}
\mathbf{A}^{\dagger}=\left(\mathbf{A}^{\top} \mathbf{A}\right)^{-1} \mathbf{A}^{\top}
$$

which is the same expression as arises in the normal equations (see Section 11.2.2.1). In this case, $\mathbf{A}^{\dagger}$ is a left inverse of $\mathbf{A}$ because
$$\large\tag{3}
\mathbf{A}^{\dagger} \mathbf{A}=\left(\mathbf{A}^{\top} \mathbf{A}\right)^{-1} \mathbf{A}^{\top} \mathbf{A}=\mathbf{I}
$$
but is not a right inverse because
$$\large\tag{4}
\mathbf{A} \mathbf{A}^{\dagger}=\mathbf{A}\left(\mathbf{A}^{\top} \mathbf{A}\right)^{-1} \mathbf{A}^{\top}
$$
only has rank $n$, and so cannot be the $m \times m$ identity matrix.
If $m<n$ (short. fat) and the rows of $\mathbf{A}$ are linearly independent (so $\mathbf{A}^{\top}$ is full rank), then the pseudo inverse is

$$\large\tag{5}
\mathbf{A}^{\hat{\dagger}}=\mathbf{A}^{\top}\left(\mathbf{A} \mathbf{A}^{\top}\right)^{-1}
$$

In this case, $\mathbf{A}^{\dagger}$ is a right inverse of $\mathbf{A}$.
We can compute the pseudo inverse using the SVD decomposition $\mathbf{A}=$ USV $^{\top}$. In particular, one can show that

$$\large
\mathbf{A}^{\dagger}=\mathbf{V}\left[\operatorname{diag}\left(1 / \sigma_1, \cdots, 1 / \sigma_r, 0, \cdots, 0\right)\right] \mathbf{U}^{\top}=\mathbf{V S}^{-1} \mathbf{U}^{\top}
$$

where $r$ is the rank of the matrix, and where we define $\mathbf{S}^{-1}=\operatorname{diag}\left(\sigma_1^{-1}, \ldots, \sigma_r^{-1}, 0, \ldots, 0\right)$. Indeed if the matrices were square and full rank we would have

$$
\left(\mathbf{U S V}^{\top}\right)^{-1}=\mathbf{V S}^{-1} \mathbf{U}^{\top}
$$