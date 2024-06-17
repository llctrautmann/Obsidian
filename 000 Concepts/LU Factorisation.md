---
title: LU Factorisation
date:
  - 17-06-2024
time: 11:44
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
🍙: いや
type: 
formula: 
aliases: 
modified: 2024-06-17
---
# LU Factorisation
Any square matrix can be factorised into an upper and lower triangular matrix. 

$$ \large\tag{1}
\left[\begin{array}{lll}
a_{11} & a_{12} & a_{13} \\
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33}
\end{array}\right]=\left[\begin{array}{ccc}
l_{11} & 0 & 0 \\
l_{21} & l_{22} & 0 \\
l_{31} & l_{32} & l_{33}
\end{array}\right]\left[\begin{array}{ccc}
u_{11} & u_{12} & u_{13} \\
0 & u_{22} & u_{23} \\
0 & 0 & u_{33}
\end{array}\right] .
$$

- This can require some row permutation to avoid singularity
	- would happen if some diagonal entry is 0 as the column would be zero and the matrix would not be full rank. 
	- This is called **patrial pivoting**

