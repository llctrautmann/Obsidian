---
title: power method appendix
date:
  - 14-06-2024
time: 19:51
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
🍙: いや
type: Appendix
formula: 
aliases: 
modified: 2024-06-14
---
Certainly! Here is the entire breakdown of the power method using $ signs to delimit math equations:

### Power Method Breakdown

1. **Matrix with Orthonormal Eigenvectors**:
	- Let $\mathbf{A}$ be a matrix with orthonormal eigenvectors $\boldsymbol{u}_i$ and eigenvalues $\lambda_i$ such that $|\lambda_1| > |\lambda_2| \geq \cdots \geq |\lambda_m| \geq 0$.
	- This means $\mathbf{A}$ can be decomposed as $\mathbf{A} = \mathbf{U} \boldsymbol{\Lambda} \mathbf{U}^{\top}$, where $\mathbf{U}$ is the matrix of eigenvectors and $\boldsymbol{\Lambda}$ is the diagonal matrix of eigenvalues.
2. **Initial Vector in the Range of $\mathbf{A}$**:
	- Let $\boldsymbol{v}_{(0)}$ be an arbitrary vector in the range of $\mathbf{A}$, meaning there exists some vector $\boldsymbol{x}$ such that $\mathbf{A} \boldsymbol{x} = \boldsymbol{v}_{(0)}$.
	- We can express $\boldsymbol{v}_{(0)}$ as a linear combination of the eigenvectors of $\mathbf{A}$:
	   - $\boldsymbol{v}_0 = a_1 \boldsymbol{u}_1 + a_2 \boldsymbol{u}_2 + \cdots + a_m \boldsymbol{u}_m$
	   - where $a_i$ are some constants.

3. **Applying $\mathbf{A}$ to $\boldsymbol{v}_0$**:
- When we apply $\mathbf{A}$ to $\boldsymbol{v}_0$, we use the linearity of matrix multiplication:
	- $\mathbf{A} \boldsymbol{v}_0 = \mathbf{A} (a_1 \boldsymbol{u}_1 + a_2 \boldsymbol{u}_2 + \cdots + a_m \boldsymbol{u}_m)$
- By the distributive property of matrix multiplication, this becomes:
	 - $\mathbf{A} \boldsymbol{v}_0 = a_1 \mathbf{A} \boldsymbol{u}_1 + a_2 \mathbf{A} \boldsymbol{u}_2 + \cdots + a_m \mathbf{A} \boldsymbol{u}_m$
	
4. **Substitution Using the Eigenvalue Equation**:
- Using the eigenvalue equation $\mathbf{A} \boldsymbol{u}_i = \lambda_i \boldsymbol{u}_i$, we substitute $\mathbf{A} \boldsymbol{u}_i$ with $\lambda_i \boldsymbol{u}_i$:
	- $\mathbf{A} \boldsymbol{v}_0 = a_1 \lambda_1 \boldsymbol{u}_1 + a_2 \lambda_2 \boldsymbol{u}_2 + \cdots + a_m \lambda_m \boldsymbol{u}_m$

5. **Iterative Multiplication and Renormalization**:
	- We repeatedly multiply $\boldsymbol{v}$ by $\mathbf{A}$ and renormalize at each step for numerical stability:
		- $\boldsymbol{v}_t \propto \mathbf{A} \boldsymbol{v}_{t-1}$
	- Since $\boldsymbol{v}_t$ is a multiple of $\mathbf{A}^t \boldsymbol{v}_0$, we have:
		- $\boldsymbol{v}_t \propto \mathbf{A}^t \boldsymbol{v}_0$

6. **Expression in Terms of Eigenvectors and Eigenvalues**:
- Expanding $\mathbf{A}^t \boldsymbol{v}_0$ in terms of the eigenvectors and eigenvalues:
	 - $\boldsymbol{v}_t \propto a_1 \lambda_1^t \boldsymbol{u}_1 + a_2 \lambda_2^t \boldsymbol{u}_2 + \cdots + a_m \lambda_m^t \boldsymbol{u}_m$
- Factoring out $\lambda_1^t$:
     \[
     \boldsymbol{v}_t \propto \lambda_1^t \left( a_1 \boldsymbol{u}_1 + a_2 \left(\frac{\lambda_2}{\lambda_1}\right)^t \boldsymbol{u}_2 + \cdots + a_m \left(\frac{\lambda_m}{\lambda_1}\right)^t \boldsymbol{u}_m \right)
     \]

7. **Convergence to the Dominant Eigenvector**:
   - As $t$ increases, $\left(\frac{\lambda_i}{\lambda_1}\right)^t$ for $i \geq 2$ will approach zero because $|\lambda_i| < |\lambda_1|$.
   - Therefore, the terms involving $\boldsymbol{u}_2, \boldsymbol{u}_3, \ldots, \boldsymbol{u}_m$ will diminish, leaving:
     \[
     \boldsymbol{v}_t \rightarrow \lambda_1^t a_1 \boldsymbol{u}_1
     \]

By normalizing at each step, $\boldsymbol{v}_t$ converges to the dominant eigenvector $\boldsymbol{u}_1$.

### Conclusion

Through repeated multiplication by $\mathbf{A}$ and normalization, the vector $\boldsymbol{v}_t$ converges to the dominant eigenvector of $\mathbf{A}$, which corresponds to the largest eigenvalue $\lambda_1$.