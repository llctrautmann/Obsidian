---
title: Positive Definite Matrices
date:
  - 27-05-2024
time: 16:37
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
🍙: いや
type: 
formula: $$\mathbf{x}^{\top} \mathbf{A} \mathbf{x} \geq 0$$
aliases:
  - positive semi-definite
modified: 2024-06-12
---
# Positive Semi-definite Matrices
## Definition
A matrix A for which the quadratic form is always positive is called **positive semi-definite**. Conversely, any matrix for which the quadratic from is negative is called **negative semi-definite**. Any matrix that has both positive and negative scalar outcomes are called **indefinite**.


## Conditions
- This is relevant only for square matrices. 
- The only real condition is
$$\mathbf{x}^{\top} \mathbf{A} \mathbf{x} \geq 0$$
- for real, symmetric matrices it is possible to show that iif the matrix is diagonally dominant ($\left|a_{i i}\right|>\sum_{j \neq i}\left|a_{i j}\right|$ for all $i$) the matrix is positive definite. 

## Noteworthy
- One important positive definite matrix is the Gram Matrix $\mathbf{G}= \mathbf{A}^{\top}\mathbf{A}$. Regardless of the dimensionality of the matrix, it's Gram matrix is always positive definite. 

