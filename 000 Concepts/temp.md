---
title: temp
date:
  - 24-05-2024
time: 23:48
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
status: Incomplete
type: 
formula: 
🍙: いや
modified: 2024-05-24
---
# temp

## Matrix Multiplication

the product of two matrices is another matrix

$$\large\tag{1}
\mathbf{C}=\mathbf{A} \mathbf{B} \in \mathbb{R}^{m \times p}
$$
where
$$\large\tag{2}
C_{i j}=\sum_{k=1}^n A_{i k} B_{k j}
$$

> [!PDF|yellow] [[murphy2022.pdf#page=270&selection=172,0,180,1&color=yellow|murphy2022, p.240]]
> > Note that in order for the matrix product to exist, the number of columns in A must equal the number of rows in B.

matmul is associative and distributiv but ususally not commutative (ab != ba)

## Vec Vec Mul

$$\large\tag{2}
\langle\boldsymbol{x}, \boldsymbol{y}\rangle \triangleq \boldsymbol{x}^{\top} \boldsymbol{y}=\sum_{i=1}^n x_i y_i
$$



