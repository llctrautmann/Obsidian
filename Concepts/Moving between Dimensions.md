---
title: Moving between Dimensions
date:
  - 02-04-2024
time: 10:26
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
chapter: 3
status: Incomplete
modified: 2024-04-02
---
# Moving between Dimensions
Any linear transformation allows vectors to be moved between dimensional spaces. This can be represented as:

$$

\mathbf{A}\mathbf{x} = f(\mathbf{x})

$$

where

$$

f: \mathbb{R}^m \to \mathbb{R}^n

$$

and $A$ is an $n \times m$ matrix that represents the linear transformation $f$, mapping vectors from $\mathbb{R}^m$ to $\mathbb{R}^n$.

The number of rows in the transformation matrix will define the dimensionality of the new vector space. 

## Examples
Moves from $\mathbb{R}^3$ to $\mathbb{R}^4$.
$$
\mathbf{A} = \begin{pmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9 \\
10 & 11 & 12 \\
\end{pmatrix}
$$

Moves from $\mathbb{R}^3$ to $\mathbb{R}^2$.

$$
\mathbf{B} = \begin{pmatrix}
1.5 & -2.3 & 0.75 \\
4.2 & 3.14 & -5.6 \\
\end{pmatrix}
$$











