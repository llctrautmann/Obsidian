---
title: Mochi Flash Cards
date: 02-02-2024
time: 08:21
author: Luca Trautmann
tags: 
series: 
chapter: 
modified: 2024-05-27
---
# What is the relationship of a Distance and Metric in Lin. Alg?

Consider an inner product space $(V,\langle\cdot, \cdot\rangle)$. Then
$$
d(x, y):=\|x-y\|=\sqrt{\langle x-y, x-y\rangle}
$$
This is called the distance between the vectors $x$ and $y$.

`Note: the distance is the norm between the difference between two vectors.`


# Define the Transpose of a Matrix
If $\mathbf{A} \in \mathbb{R}^{m \times n}$, its transpose $\mathbf{A}^{\top} \in \mathbb{R}^{n \times m}$ is given by $\left(\mathbf{A}^{\top}\right)_{i j}=A_{j i}$ for each $(i, j)$. In other words, the columns of $\mathbf{A}$ become the rows of $\mathbf{A}^{\top}$, and the rows of $\mathbf{A}$ become the columns of $\mathbf{A}^{\top}$.

# What does this say in mathematical notation $\operatorname{null}(T)=\{\mathbf{v} \in V \mid T \mathbf{v}=\mathbf{0}\}$?
The null space is all vectors in V that satisify the condition that the linear map V times the vector result in the zero vector.

# What is the translation of this sign $\exists$ ?
exists

# Can we build a Dr. House model? 
One thought I am having here is: Does there exist a risk, that we have models converge on the most prevalent diseases, because we have the most data on these types of illnesses. And on the other hand can we build a model that is more akin to Dr. House? In the sense that we want to find rare diseases as well. What would that mean mathematically? What would we need to pay attention to?

# What condition needs to be met for linear independence between vectors?
A set of vectors $\mathbf{v}_1, \ldots, \mathbf{v}_n \in V$ is said to be linearly independent if

$$
\alpha_1 \mathbf{v}_1+\cdots+\alpha_n \mathbf{v}_n=\mathbf{0} \quad \text { implies } \quad \alpha_1=\cdots=\alpha_n=0
$$

`The basic idea is that linearly independent vectors can only have the trivial solution with all coefficients being 0.`

*Example*:
The vector $x_{1}= \left[ 1,2,0\right]^\top$ and $x_{2}= \left[ 2,4,0\right]^\top$ are not linearly independent and hence I can write $2x_{1}-1x_{2}=\mathbf{0}$. But $[0,1]^\top$ and $[1,0]^\top$ are linearly independent and hence the only solution possible is the trivial solution $0x_{1}-0x_{2}=\mathbf{0}$. 

# What are Inner Products and what conditions need to be met?
Inner Products are functions from [[Vector Spaces]] to the real line. 
$$\large
\langle\cdot, \cdot\rangle: V \times V \rightarrow \mathbb{R}
$$

There are three conditions: 

1. Positive: 
   $\langle\mathbf{x}, \mathbf{x}\rangle \geq 0$, with equality if and only if $\mathbf{x}=\mathbf{0}$
   
2. Linearity in the first slot: $$\langle\mathbf{x}+\mathbf{y}, \mathbf{z}\rangle=\langle\mathbf{x}, \mathbf{z}\rangle+\langle\mathbf{y}, \mathbf{z}\rangle \quad \text{and} \quad \langle\alpha \mathbf{x}, \mathbf{y}\rangle=\alpha\langle\mathbf{x}, \mathbf{y}\rangle$$
3. Symmetry
$$
\langle\mathbf{x}, \mathbf{y}\rangle=\langle\mathbf{y}, \mathbf{x}\rangle
$$

# What are the two important properties of Homomorphisms? 
1. Closure under addition related to associativity
2. Closure under scalar multiplication related to distributivity

# Define Endomorphism
- **Definition**: A linear mapping from a vector space to itself.
- **Form**: $\Phi: V \rightarrow V$
- **Properties**:
  - Preserves vector addition and scalar multiplication.
  - Does not need to be bijective (can be injective, surjective, both, or neither).

# Define Isomorphism
### Isomorphism
- **Definition**: A linear mapping between two vector spaces that is bijective.
- **Form**: $\Phi: V \rightarrow W$.
- **Properties**:
  - Preserves vector addition and scalar multiplication.
  - **Bijective**: One-to-one (injective) and onto (surjective).
  - Has an inverse mapping $\Phi^{-1}: W \rightarrow V$ that is also linear.

# Define Automorphism
### Automorphism
- **Definition**: A bijective endomorphism.
- **Form**: $\Phi: V \rightarrow V$.
- **Properties**:
  - Preserves vector addition and scalar multiplication.
  - **Bijective**: One-to-one (injective) and onto (surjective).
  - Has an inverse mapping $(\Phi^{-1}: V \rightarrow V$ that is also linear.


# What is the formula for eigenthings?

$$\mathbf{A}\mathbf{x}= \lambda \mathbf{x}$$


# How do Eigenvectors and Eigenvalues behave wrt. scaling by a real-valued scalar?
Eigenvalues are infinitely scalable by a scalar, so $c\mathbf{u}$ is also an eigenvector. 
$$\large
\mathbf{A}(c \boldsymbol{u})=c \mathbf{A} \boldsymbol{u}=c \lambda \boldsymbol{u}=\lambda(c \boldsymbol{u})
$$


# What does a Inner Product enable in Linear Algebra? 
**Inner products allow for the introduction of intuitive geometrical concepts, such as the length of a vector and the angle or distance between two vectors.** A major purpose of inner products is to determine whether vectors are orthogonal to each other.