---
title: Geometry of Linear Algebra
date:
  - 01-04-2024
time: 15:51
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
chapter: 1
status: Complete
modified: 2024-04-01
link: https://gregorygundersen.com/blog/2018/10/24/matrices/
---
# Geometry of Linear Algebra
## Matrices as Linear Transformations
The basic problem linear Algebra tries to solve is the following:

$$
\operatorname{b}= \operatorname{A}x
$$
Where $\mathbf{b} \in \mathrm{R}^m, A \in \mathrm{R}^{m \times n}$, and $\mathbf{x} \in \mathrm{R}^n$.

### What do these components mean?

$\operatorname{x}$ = the solution to the system of linear equations
$\operatorname{A}$ = the system of $m$ linear equations with $n$ variables
$b$ = the output we want to achive

### An alternative and more intuitive explanation
Alternatively, I can think about A as a **linear function**. 

$$f(\mathbf{x})=A \mathbf{x}$$

#### Background 
One fundamental idea that I should always keep in mind is that the columns of a matrix show me where the standard basis vectors in $\mathrm{R}^n$ land in the solution space $\mathrm{R}^m$.

*Example*: 
The standard basis vectors in $\mathrm{R}^3$ are:

$$\mathbf{e}_1=\left[\begin{array}{l}1 \\ 0 \\ 0\end{array}\right] \quad \mathbf{e}_2=\left[\begin{array}{l}0 \\ 1 \\ 0\end{array}\right] \quad \mathbf{e}_3=\left[\begin{array}{l}0 \\ 0 \\ 1\end{array}\right]$$

This means by definition, that ever vector in $\mathrm{R}^3$ are a combination of the basis vectors.

$$\mathbf{x}=\left[\begin{array}{l}x_1 \\ x_2 \\ x_3\end{array}\right]=x_1\left[\begin{array}{l}1 \\ 0 \\ 0\end{array}\right]+x_2\left[\begin{array}{l}0 \\ 1 \\ 0\end{array}\right]+x_3\left[\begin{array}{l}0 \\ 0 \\ 1\end{array}\right]$$

What happens when I matrix multiply one of the basis vectors with a transformation matrix? 

$$\overbrace{\left[\begin{array}{c|c|c}1 & 2 & 0 \\ -5 & 3 & 1\end{array}\right]}^A \overbrace{\left[\begin{array}{l}0 \\ 1 \\ 0\end{array}\right]}^{\mathbf{e_{2}}}=\left[\begin{array}{l}0+2+0 \\ 0+3+0\end{array}\right]=\left[\begin{array}{l}2 \\ 3\end{array}\right]$$
So in the transformed space, the original basis vector $\mathbf{e}_2$ is now the vector $\left[\begin{array}{l}2 \\ 3\end{array}\right]$. So for all basis vectors I can therefore deduce: 

$$\left[\begin{array}{c|c|c}1 & 2 & 0 \\ -5 & 3 & 1\end{array}\right]\left[\begin{array}{l|l|l}1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1\end{array}\right]=\left[\begin{array}{c|c|c}1 & 2 & 0 \\ -5 & 3 & 1\end{array}\right]$$
The result is a matrix that shows me, where all basis vectors in $\mathrm{R}^3$ will land in $\mathrm{R}^2$.

When we perform matrix multiplication, we are projecting a vector or vectors into a new space defined by the columns of the transformation matrix $\operatorname{A}$. And $f(x)$ is just a _linear combination of the columns of $A$_, where the coefficients are the components of $x$.

$$\begin{aligned} & \overbrace{\left[\begin{array}{c|c|c}1 & 2 & 0 \\ -5 & 3 & 1 \\\end{array}\right]}^A \overbrace{\left[\begin{array}{c}1.2 \\ 1.5 \\ -2\end{array}\right]}^{\mathbf{x}}=\overbrace{\left[\begin{array}{c}4.2 \\ -3.5\end{array}\right]}^{f(\mathbf{x})} \\ & 1.2 \overbrace{\left[\begin{array}{c}1 \\ -5\end{array}\right]}^{f\left(\mathbf{e}_1\right)}+1.5 \overbrace{\left[\begin{array}{l}2 \\ 3\end{array}\right]}^{f\left(\mathbf{e}_2\right)}-2 \overbrace{\left[\begin{array}{l}0 \\ 1\end{array}\right]}^{f\left(\mathbf{e}_3\right)}=\left[\begin{array}{c}1.2+3+0 \\ -6+4.5-2\end{array}\right]=\overbrace{\left[\begin{array}{c}4.2 \\ -3.5\end{array}\right]}^{f(x)} \\ & \end{aligned}$$
Two things are the conclusion of these two formulae:

1. The transformation matrix $A$ is a transformation of the standard basis vectors and the columns of A show the original basis vectors in the transformed space.
2. Seeing $A$ as a function $A = f:\mathbf{R}^n \to \mathbf{R}^m$, we see that $f(x)$ is a linear combination of the transformed basis vectors. 



