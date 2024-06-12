---
title: Properties of Linear Maps
date:
  - 12-06-2024
time: 12:26
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
🍙: いや
type: Concept
formula: 
aliases: 
modified: 2024-06-12
---
# Properties of Linear Maps
## Trace of a Sq Matrix
- see [[Trace]]

## Determinant
- see [[Determinant]]

## Rank of a Matrix
The column rank of a matrix $\mathbf{A}$ is the dimension of the space spanned by its columns, and the row rank is the dimension of the space spanned by its rows.
	- In the gaussian elimination process the rank are the number of pivot columns.
	- column rank is always equal to row rank

### Conditions
- For $\mathbf{A} \in \mathbb{R}^{m \times n}, \operatorname{rank}(\mathbf{A}) \leq \min (m, n)$. If $\operatorname{rank}(\mathbf{A})=\min (m, n)$, then $\mathbf{A}$ is said to be full rank, otherwise it is called rank deficient.
- For $\mathbf{A} \in \mathbb{R}^{m \times n}, \operatorname{rank}(\mathbf{A})=\operatorname{rank}\left(\mathbf{A}^{\top}\right)=\operatorname{rank}\left(\mathbf{A}^{\top} \mathbf{A}\right)=\operatorname{rank}\left(\mathbf{A} \mathbf{A}^{\top}\right)$
- For $\mathbf{A} \in \mathbb{R}^{m \times n}, \mathbf{B} \in \mathbb{R}^{n \times p}, \operatorname{rank}(\mathbf{A B}) \leq \min (\operatorname{rank}(\mathbf{A}), \operatorname{rank}(\mathbf{B}))$.
- For $\mathbf{A}, \mathbf{B} \in \mathbb{R}^{m \times n}, \operatorname{rank}(\mathbf{A}+\mathbf{B}) \leq \operatorname{rank}(\mathbf{A})+\operatorname{rank}(\mathbf{B})$.

## Condition Number
The condition number indicates the stability of a matrix[^1]. 

$$\large\tag{1}\kappa(\mathbf{A}) \triangleq\|\mathbf{A}\| \cdot\left\|\mathbf{A}^{-1}\right\|$$

The condition number in case of the $\mathbf{}{l}_{2}$-norm is the ratio of the largest to the smallest singular value [^2]. Alternatively it is the ratio between largest and the smallest eigenvalue. 

$$\large\tag{2}\kappa(\mathbf{A})=\sigma_{\max } / \sigma_{\min }=\sqrt{\frac{\lambda_{\max }}{\lambda_{\min }}}$$


# Footnotes

[^1]: [[murphy2022.pdf#page=266&selection=45,0,58,8|murphy2022, p.236]] 
[^2]: [[murphy2022.pdf#page=266&selection=409,0,433,8&color=yellow|murphy2022, p.236]]