---
title: Single Value Decomposition
date:
  - 15-06-2024
time: 14:00
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
🍙: いや
type: 
formula: 
aliases: 
modified: 2024-06-15
---
# Single Value Decomposition
The single value decomposition is a generalisation of the [[Eigenvalue decomposition|EVD]] to any real values matrix.


## Basics

$$\Large\tag{1}
\mathbf{A}=\mathbf{U S V}^{\top}=\sigma_1\left(\begin{array}{c}
\mid \\
u_1 \\
\mid
\end{array}\right)\left(\begin{array}{lll}
- & v_1^{\top} & -
\end{array}\right)+\cdots+\sigma_r\left(\begin{array}{c}
\mid \\
u_r \\
\mid
\end{array}\right)\left(\begin{array}{lll}
- & v_r^{\top} & -
\end{array}\right)
$$

- $\mathbf{U}$ is a orthonormal square matrix ($\mathbf{U}^{\top}\mathbf{U}=\mathbf{0}$)
- S is a matrix with singular values on the diagonal
	- $min(n,m)$ singular values
- V is a orthonormal square matrix  ($\mathbf{V}^{\top}\mathbf{V}=\mathbf{0}$)  [^2]

There is a less computationally intensive thin SVD[^3]. 

## Connecting EVD and SVD
If $\mathbf{A}$ is real, symmetric and positive-definite, SVD is equal to EVD [^1]. 

$$ \large\tag{2}
\mathbf{A}=\mathbf{U S V}^{\top}=\mathbf{U S U}^{\top}=\mathbf{U S U}^{-1}
$$
In the more general case I do not get this results but instead

$$ \large\tag{3}
\mathbf{A}^{\top} \mathbf{A}=\mathbf{V S}^{\top} \mathbf{U}^{\top} \mathbf{U S} \mathbf{V}^{\top}=\mathbf{V}\left(\mathbf{S}^{\top} \mathbf{S}\right) \mathbf{V}^{\top}
$$

$$\mathbf{V}\mathbf{D}=\mathbf{V}\Lambda$$

# Footnotes

[^1]: [[murphy2022.pdf#page=288&selection=212,0,217,69&color=yellow|murphy2022, p.258]] 
[^2]: [[murphy2022.pdf#page=288&selection=21,0,103,60&color=yellow|murphy2022, p.258]] 
[^3]: [[murphy2022.pdf#page=288&selection=145,53,172,1&color=yellow|murphy2022, p.258]] 