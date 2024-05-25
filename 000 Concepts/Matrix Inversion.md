---
title: Matrix Inversion
date:
  - 25-05-2024
time: 08:46
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
status: Incomplete
type: Concept
formula: $\mathbf{A}^{-1} \mathbf{A}=\mathbf{I}=\mathbf{A} \mathbf{A}^{-1}$
🍙: いや
modified: 2024-05-25
---
# Matrix Inversion
Determinants are only defined for square matrices. For these matrices a determinant is a function that maps $A$ onto $\mathbb{R}$. The inverse of a Matrix is strictly only defined for [square matrices](Fundamental%20Linear%20Maps).

$$\large\tag{1}
\mathbf{A}^{-1} \mathbf{A}=\mathbf{I}=\mathbf{A} \mathbf{A}^{-1}
$$


## Conditions
- applies only to square matrices
- requires $\\det(A) \neg 0$ otherwise the matrix is singular, and squeezes a dimension. Determinants are therefore a measure of volume, which also explains why invertible matrices need a non-zero determinant. If the determinant is zero the volume is reduced to at least a plane. 

> [!PDF|yellow] [[deisenroth2020.pdf#page=107&selection=150,2,164,1&color=yellow|deisenroth2020, p.101]]
> > It turns out that the determinant det(A) is the signed volume of an n-dimensional parallelepiped formed by columns of the matrix A.
> 
> This also explains why a matrix with a det(M) = 0 is so problematic. These matrices are not staying within the geometric space, but transform, the input onto a lower dimensional space. __Thus, the determinant acts as a function that measures the signed volume formed by column vectors composed in a matrix.__


## Rules for Inverse $A^{-1}$
There exist some fundamental rules for matrices, that follow from general principles of exponents as well as the three general axioms (dist, asso, comu) . 

$$\large\tag{2}
\begin{aligned}
\left(\mathbf{A}^{-1}\right)^{-1} & =\mathbf{A} \\
(\mathbf{A B})^{-1} & =\mathbf{B}^{-1} \mathbf{A}^{-1} \\
\left(\mathbf{A}^{-1}\right)^{\top} & =\left(\mathbf{A}^{\top}\right)^{-1} \triangleq \mathbf{A}^{-T}
\end{aligned}
$$





The equation \((2 \cdot 3)^2 = 2^2 \cdot 3^2\) holds due to the properties of exponents and the distributive property of multiplication over addition. Here are the fundamental axioms and properties underpinning this rule:

1. **Exponentiation and Multiplication**:
   - For any real numbers \(a\) and \(b\), and any integer \(n\), \((a \cdot b)^n = a^n \cdot b^n\). This is a general property of exponents.

2. **Distributive Property**:
   - The distributive property states that \(a \cdot (b + c) = a \cdot b + a \cdot c\). While this property is more directly related to addition and multiplication, it underpins the way we handle operations within parentheses.

### Proof Using Properties of Exponents

Given \((2 \cdot 3)^2\):

1. **Apply the exponent to the product**:
   \[
   (2 \cdot 3)^2 = (2 \cdot 3) \cdot (2 \cdot 3)
   \]

2. **Distribute the multiplication**:
   \[
   (2 \cdot 3) \cdot (2 \cdot 3) = 2 \cdot 3 \cdot 2 \cdot 3
   \]

3. **Rearrange the factors (associative property of multiplication)**:
   \[
   2 \cdot 2 \cdot 3 \cdot 3 = 2^2 \cdot 3^2
   \]

Thus, \((2 \cdot 3)^2 = 2^2 \cdot 3^2\).

### Fundamental Axioms

1. **Associative Property of Multiplication**:
   - \((a \cdot b) \cdot c = a \cdot (b \cdot c)\)

2. **Commutative Property of Multiplication**:
   - \(a \cdot b = b \cdot a\)

3. **Distributive Property**:
   - \(a \cdot (b + c) = a \cdot b + a \cdot c\)

4. **Exponentiation Rules**:
   - \((a \cdot b)^n = a^n \cdot b^n\)

These properties and axioms collectively ensure that the equation \((2 \cdot 3)^2 = 2^2 \cdot 3^2\) holds true.