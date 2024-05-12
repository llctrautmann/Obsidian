---
title: Linear Algebra
date:
  - 02-02-2024
time: 23:39
author: Luca Trautmann
tags: 
series: M4ML
chapter: 1
modified: 2024-05-02
status: Complete
---
# Linear Algebra
## What is an algebra?
An algebra are objects and a set of rules to manipulate them. 

## Linear Algebra Basics
Linear Algebra is are the methods and rules to manipulate vectors. In general, vectors are special objects that
1) can be added together and 
2) be multiplied by scalars to produce another object of the same kind. 

From an abstract mathematical viewpoint, any object that satisfies these two properties can be considered a vector. 

Examples are:
1) Geometrics vectors
2) More exotic: Polynomials 

## Systems of Linear Equations
[[Concepts/Linear Algebra]] at its core is a method of solving systems of linear equations. In general, for a real-valued system of linear equations we obtain either no, exactly one, or infinitely many solutions. 

There is a simple and easy to understand notation for systems of linear equations:
$$
\left[\begin{array}{c}
a_{11} \\
\vdots \\
a_{m 1}
\end{array}\right] x_1+\left[\begin{array}{c}
a_{12} \\
\vdots \\
a_{m 2}
\end{array}\right] x_2+\cdots+\left[\begin{array}{c}
a_{1 n} \\
\vdots \\
a_{m n}
\end{array}\right] x_n=\left[\begin{array}{c}
b_1 \\
\vdots \\
b_m
\end{array}\right]
\Longleftrightarrow\left[\begin{array}{ccc}a_{11} & \cdots & a_{1 n} \\ \vdots & & \vdots \\ a_{m 1} & \cdots & a_{m n}\end{array}\right]\left[\begin{array}{c}x_1 \\ \vdots \\ x_n\end{array}\right]=\left[\begin{array}{c}b_1 \\ \vdots \\ b_m\end{array}\right]
$$

> always remember matrix-matrix multiplication is basically rows times columns. 

## Matrices
The most common interpretation of a matrix is a function applied to a system of linear equations (linear mapping) but they also work as compact representations; in higher dimensions matrices become conventionally named tensors. 

### Basic Algebra Actions: Add and Multiply
Summing is conducted element-wise:

$$\boldsymbol{A}+\boldsymbol{B}:=\left[\begin{array}{ccc}a_{11}+b_{11} & \cdots & a_{1 n}+b_{1 n} \\ \vdots & & \vdots \\ a_{m 1}+b_{m 1} & \cdots & a_{m n}+b_{m n}\end{array}\right] \in \mathbb{R}^{m \times n}$$

Multiplication works by multiplying the rows of A with the Columns of B and summing the result ([[Inner Products]]). Indicated by the following expression: 
$$c_{i j}=\sum_{l=1}^n a_{i l} b_{l j}, \quad i=1, \ldots, m, \quad j=1, \ldots, k$$
The only requirement here is $\underbrace{\boldsymbol{A}}_{n \times k} \underbrace{B}_{k \times m}=\underbrace{C}_{n \times m}$. Element-wise multiplication is known as the _Hadamard product_. Matrix multiplication is not commutative so $$A B \neq B A$$

### Identity Matrix
A matrix with 1 on the diagonal and otherwise only 0. The equivalent to a 1 in Multiplications as $\operatorname{A} \times \operatorname{I} = \operatorname{A}$. 

### Basic Algebra Properties
Now that we defined matrix multiplication, matrix addition and the identity matrix, let us have a look at some properties of matrices:

- Associativity:
$$
\forall \boldsymbol{A} \in \mathbb{R}^{m \times n}, \boldsymbol{B} \in \mathbb{R}^{n \times p}, \boldsymbol{C} \in \mathbb{R}^{p \times q}:(\boldsymbol{A B}) \boldsymbol{C}=\boldsymbol{A}(\boldsymbol{B} \boldsymbol{C})
$$
- Distributivity:
$$
\begin{aligned}
\forall \boldsymbol{A}, \boldsymbol{B} \in \mathbb{R}^{m \times n}, \boldsymbol{C}, \boldsymbol{D} \in \mathbb{R}^{n \times p}:& (\boldsymbol{A}+\boldsymbol{B}) \boldsymbol{C}=\boldsymbol{A} \boldsymbol{C}+\boldsymbol{B C} \\
& \boldsymbol{A}(\boldsymbol{C}+\boldsymbol{D})=\boldsymbol{A C}+\boldsymbol{A D} \\
&
\end{aligned}
$$
- Multiplication with the identity matrix:
$$
\forall \boldsymbol{A} \in \mathbb{R}^{m \times n}: \boldsymbol{I}_m \boldsymbol{A}=\boldsymbol{A} \boldsymbol{I}_n=\boldsymbol{A}
$$

Note that $\boldsymbol{I}_m \neq \boldsymbol{I}_n$ for $m \neq n$ and $∀$ means "for all".

## Inverse and Transpose
### Inverse
For a square matrix $A \in \mathbb{R}^{n \times n}$, let $B \in \mathbb{R}^{n \times n}$ have the property $\boldsymbol{A B}=\boldsymbol{I}_n=\boldsymbol{B A}$, then $B$ is the inverse of $A$ denotes as $A^{-1}$. If matrix has an inverse it is called _regular/invertible/nonsingular_ otherwise it is called _singular/noninvertible_. When there is a matrix it is unique. 

#### Inverse of a 2 x 2 matrix
Consider a matrix
$$
\boldsymbol{A}:=\left[\begin{array}{ll}
a_{11} & a_{12} \\
a_{21} & a_{22}
\end{array}\right] \in \mathbb{R}^{2 \times 2} .
$$

If we multiply $\boldsymbol{A}$ with
$$
A^{\prime}:=\left[\begin{array}{cc}
a_{22} & -a_{12} \\
-a_{21} & a_{11}
\end{array}\right]
$$
we obtain
$$
\boldsymbol{A} \boldsymbol{A}^{\prime}=\left[\begin{array}{cc}
a_{11} a_{22}-a_{12} a_{21} & 0 \\
0 & a_{11} a_{22}-a_{12} a_{21}
\end{array}\right]=\left(a_{11} a_{22}-a_{12} a_{21}\right) \boldsymbol{I}
$$

Therefore,
$$
A^{-1}=\frac{1}{a_{11} a_{22}-a_{12} a_{21}}\left[\begin{array}{cc}
a_{22} & -a_{12} \\
-a_{21} & a_{11}
\end{array}\right]
$$
if and only if $a_{11} a_{22}-a_{12} a_{21} \neq 0$. $a_{11} a_{22}-a_{12} a_{21}$ is called the determinant.

### Transpose
The transpose can generally be obtained by switching the rows and columns of a matrix. It is abbreviated with $\boldsymbol{A}^{\top}$. If $\boldsymbol{A}^{\top}= \boldsymbol{A}^{-\top}$ the matrix is __symmetric__. 

## Multiplication by a Scalar
Scaling a matrix is conducted element-wise. 

For $\lambda, \psi \in \mathbb{R}$ the following rules hold: 

Associativity:
$$
(\lambda \psi) \boldsymbol{C}=\lambda(\psi \boldsymbol{C}), \quad \boldsymbol{C} \in \mathbb{R}^{m \times n}
$$
- $\lambda(\boldsymbol{B C})=(\lambda \boldsymbol{B}) \boldsymbol{C}=\boldsymbol{B}(\lambda \boldsymbol{C})=(\boldsymbol{B} \boldsymbol{C}) \lambda, \quad \boldsymbol{B} \in \mathbb{R}^{m \times n}, \boldsymbol{C} \in \mathbb{R}^{n \times k}$ 
	- Note that this allows us to move scalar values around.
- $(\lambda \boldsymbol{C})^{\top}=\boldsymbol{C}^{\top} \lambda^{\top}=\boldsymbol{C}^{\top} \lambda=\lambda \boldsymbol{C}^{\top}$ since $\lambda=\lambda^{\top}$ for all $\lambda \in \mathbb{R}$.

Distributivity:
$$
\begin{aligned}
& (\lambda+\psi) \boldsymbol{C}=\lambda \boldsymbol{C}+\psi \boldsymbol{C}, \quad \boldsymbol{C} \in \mathbb{R}^{m \times n} \\
& \lambda(\boldsymbol{B}+\boldsymbol{C})=\lambda \boldsymbol{B}+\lambda \boldsymbol{C}, \quad \boldsymbol{B}, \boldsymbol{C} \in \mathbb{R}^{m \times n}
\end{aligned}
$$

## Solving Systems of Linear Equations
### Particular and General Solution
A particular Solution to a system of linear equations is one unique solution to the system. 

The three steps for finding a general solutions are:

1. Find a particular solution to $\boldsymbol{A x}=\boldsymbol{b}$.
2. Find all solutions to $\boldsymbol{A x}=\mathbf{0}$.
3. Combine the solutions from steps 1. and 2. to the general solution.

### Elementary Transformations
Key to solving a system of linear equations are __elementary transformations that keep the solution set the same, but that transform the equation system into a simpler form__. 

There are three elementary transformations:
- Exchange of two equations (Matrix row)
- Multiplication of an equation (row) with a constant $\lambda \in \mathbb{R} \backslash\{0\}$
- Addition of two equations (rows)

### Row-Echolon Form and Pivots 
A matrix is in row-echelon form if:
- All rows that contain only zeros are at the bottom of the matrix; correspondingly, all rows that contain at least one nonzero element are on top of rows that contain only zeros.
- Looking at nonzero rows only, the first nonzero number from the left (also called the pivot or the leading coefficient) is always strictly to the right of the pivot of the row above it.
`\\ This is the staircase form I have already studied in Strangs course`

![[REF_linalg.png#invert]]
`Note: The pivot columns and the free columns without a pivot

Pivots are the integers with from the left that have only leading zeros as shown above. The variables corresponding to the pivots in the row-echelon form are called basic variables and the other basic variable variables are free variables. For example, $x1, x3, x4$ are basic free variable variables, whereas $x2, x5$ are free variables.

> The row-echelon form makes our lives easier when we need to determine a __particular solution__. To do this, we express the right-hand side of the equation system using the pivot columns. (Deisenroth et al., 2020, p. 31)

>[!REF Recipe]+
> 1. Use the elementary transformations to rearrange the rows of the matrix and determine the pivots
> 2. Free variables will have their $x$ values set to 0.
> 3. The pivot columns and their $\lambda$ parameters added together need to form the general solution
> 4. The task gets easier in Reduced REF. (all pivots = 1 and the pivot is the only non-zero value in each column)

Gaussian elimination reduces a matrix into its RLEF.

### Example reduced Row-Echolon Form
$$
\boldsymbol{A}=\left[\begin{array}{ccccc}1 & 3 & 0 & 0 & 3 \\ 0 & 0 & \mathbf{1} & 0 & 9 \\ 0 & 0 & 0 & 1 & -4\end{array}\right]
$$

The key idea for finding the solutions of Ax = 0 is to look at the nonpivot columns, which we will need to express as a (linear) combination of the pivot columns.

### The Minus-1 Trick
We can also just take the original matrix and add as many rows with -1 in the missing pivot position as we have free variables so that the diagonal is only 1s and -1s and get the solution immediately. 

$$\boldsymbol{A}=\left[\begin{array}{ccccc}1 & 3 & 0 & 0 & 3 \\ 0 & 0 & 1 & 0 & 9 \\ 0 & 0 & 0 & 1 & -4\end{array}\right]$$
will lead to: 
$$\tilde{\boldsymbol{A}}=\left[\begin{array}{ccccc}1 & 3 & 0 & 0 & 3 \\ 0 & -1 & 0 & 0 & 0 \\ 0 & 0 & 1 & 0 & 9 \\ 0 & 0 & 0 & 1 & -4 \\ 0 & 0 & 0 & 0 & -1\end{array}\right]$$
The solution will then be just the columns of the free variables.
$$\left\{\boldsymbol{x} \in \mathbb{R}^5: \boldsymbol{x}=\lambda_1\left[\begin{array}{c}3 \\ -1 \\ 0 \\ 0 \\ 0\end{array}\right]+\lambda_2\left[\begin{array}{c}3 \\ 0 \\ 9 \\ -4 \\ -1\end{array}\right], \quad \lambda_1, \lambda_2 \in \mathbb{R}\right\}$$ $\square$

### Calculating the Inverse
![[Inverse_Calcuation.png]]

### Algorithms for solving a system of linear equations
`// I will consciously leave this part out. But if the need arises, the keyword here is Moore-Penrose pseudo-inverse or Gauß-Seidel`

## Vector Spaces
### Formal Definition of Vectors: Groups
A group is a set of elements and an operation defined on these elements that keeps some structure of the set intact. 

 __Group__. Consider a set $\mathcal{G}$ and an operation $\otimes: \mathcal{G} \times \mathcal{G} \rightarrow \mathcal{G}$ defined on $\mathcal{G}$. Then $G:=(\mathcal{G}, \otimes)$ is called a group if the following hold:

1. Closure of $\mathcal{G}$ under $\otimes: \forall x, y \in \mathcal{G}: x \otimes y \in \mathcal{G}$ `\\ Stays the same kind`
2. Associativity: $\forall x, y, z \in \mathcal{G}:(x \otimes y) \otimes z=x \otimes(y \otimes z)$ 
3. Neutral element: $\exists e \in \mathcal{G} \forall x \in \mathcal{G}: x \otimes e=x$ and $e \otimes x=x$ `\\ 1 for example`
4. Inverse element: $\forall x \in \mathcal{G} \exists y \in \mathcal{G}: x \otimes y=e$ and $y \otimes x=e$, where $e$ is the neutral element. We often write $x^{-1}$ to denote the inverse element of $x$. 

Note: The inverse element is defined wrt the operation not the element and does not necessarily mean $\frac{1}{x}$. 

__Abelian Group__: If additionally $\forall x, y \in \mathcal{G}: x \otimes y=y \otimes x$, then $G=(\mathcal{G}, \otimes)$ is an Abeliar group (commutative).

__General Linear Group__: The set of regular (invertible) matrices $\boldsymbol{A} \in \mathbb{R}^{n \times n}$ is a group with respect to matrix multiplication is called general linear group $G L(n, \mathbb{R})$. However, since matrix multiplication is not commutative, the group is not Abelian.

## Vector Spaces
For a vector space to exist, we need an inner operation (mapping of $\mathcal{G} \times \mathcal{G} \rightarrow \mathcal{G}$) and an outer operation (e.g. the multiplication of a vector with a scalar). 

> [!Define]+
> Definition 2.9 (Vector Space). A real-valued vector space $V=(\mathcal{V},+, \cdot)$ is a set $\mathcal{V}$ with two operations
> $$
> \begin{aligned}
> & +: \mathcal{V} \times \mathcal{V} \rightarrow \mathcal{V} \\
> & \quad: \mathbb{R} \times \mathcal{V} \rightarrow \mathcal{V}
> \end{aligned}
> $$
> where
> 1. $(\mathcal{V},+)$ is an Abelian group
> 2. Distributivity:
> 1. $\forall \lambda \in \mathbb{R}, \boldsymbol{x}, \boldsymbol{y} \in \mathcal{V}: \lambda \cdot(\boldsymbol{x}+\boldsymbol{y})=\lambda \cdot \boldsymbol{x}+\lambda \cdot \boldsymbol{y}$
> 2. $\forall \lambda, \psi \in \mathbb{R}, \boldsymbol{x} \in \mathcal{V}:(\lambda+\psi) \cdot \boldsymbol{x}=\lambda \cdot \boldsymbol{x}+\psi \cdot \boldsymbol{x}$
> 3. Associativity (outer operation): $\forall \lambda, \psi \in \mathbb{R}, \boldsymbol{x} \in \mathcal{V}: \lambda \cdot(\psi \cdot \boldsymbol{x})=(\lambda \psi) \cdot \boldsymbol{x}$
> 4. Neutral element with respect to the outer operation: $\forall \boldsymbol{x} \in \mathcal{V}: 1 \cdot \boldsymbol{x}=\boldsymbol{x}$

The elements $x \in V$ are called vectors. The neutral element of $(\mathcal{V},+)$ is the zero vector $0=[0, \ldots, 0]^{\top}$, and the inner operation + is called vector addition. The elements $\lambda \in \mathbb{R}$ are called scalars and the outer operation is a multiplication by scalars. 

## Vector Subspaces
Subspaces are spaces within a vector space that, when vector space operation are performed on subspace vectors, stay within the subspace. 

> [!Define]+
> Definition 2.10 (Vector Subspace). Let $V=(\mathcal{V},+, \cdot)$ be a vector space and $\mathcal{U} \subseteq \mathcal{V}, \mathcal{U} \neq \emptyset$. Then $U=(\mathcal{U},+, \cdot)$ is called vector subspace of $V$ (or linear subspace) if $U$ is a vector space with the vector space operations + and $\times$ restricted to $\mathcal{U} \times \mathcal{U}$ and $\mathbb{R} \times \mathcal{U}$. We write $U \subseteq V$ to denote a subspace $U$ of $V$.
> 
> If $\mathcal{U} \subseteq \mathcal{V}$ and $V$ is a vector space, then $U$ naturally inherits many properties directly from $V$ because they hold for all $\boldsymbol{x} \in \mathcal{V}$, and in particular for all $x \in \mathcal{U} \subseteq \mathcal{V}$. This includes the Abelian group properties, the distributivity, the associativity and the neutral element. To determine whether $(\mathcal{U},+, \cdot)$ is a subspace of $V$ we still do need to show
> 1. $\mathcal{U} \neq \emptyset$, in particular: $\mathbf{0} \in \mathcal{U}$
> 2. Closure of $U$ :
> a. With respect to the outer operation: $\forall \lambda \in \mathbb{R} \forall \boldsymbol{x} \in \mathcal{U}: \lambda \boldsymbol{x} \in \mathcal{U}$.
> b. With respect to the inner operation: $\forall \boldsymbol{x}, \boldsymbol{y} \in \mathcal{U}: \boldsymbol{x}+\boldsymbol{y} \in \mathcal{U}$.


## Linear Independence 
The two important operations that are possible with vectors of a subspace are: 

- addition 
- multiplication 

__Basis__: set of vectors with which we can represent every vector in the vector space by adding them together and scaling them.

> [!Define]+
> Definition 2.11 (Linear Combination). Consider a vector space $V$ and a finite number of vectors $\boldsymbol{x}_1, \ldots, \boldsymbol{x}_k \in V$. Then, every $\boldsymbol{v} \in V$ of the form
> $$
> \boldsymbol{v}=\lambda_1 \boldsymbol{x}_1+\cdots+\lambda_k \boldsymbol{x}_k=\sum_{i=1}^k \lambda_i \boldsymbol{x}_i \in V
> $$
> with $\lambda_1, \ldots, \lambda_k \in \mathbb{R}$ is a linear combination of the vectors $\boldsymbol{x}_1, \ldots, \boldsymbol{x}_k$.

<mark class="hltr-red">Note</mark>: The $\mathbf{0}$-vector can always be written as the linear combination of $k$ vectors $\boldsymbol{x}_1, \ldots, \boldsymbol{x}_k$ because $\mathbf{0}=\sum_{i=1}^k 0 \boldsymbol{x}_i$ is always true. 

> [!Define]+
> Definition 2.12 (Linear (In)dependence). Let us consider a vector space $V$ with $k \in \mathbb{N}$ and $\boldsymbol{x}_1, \ldots, \boldsymbol{x}_k \in V$. If there is a non-trivial linear combination, such that $\mathbf{0}=\sum_{i=1}^k \lambda_i \boldsymbol{x}_i$ with at least one $\lambda_i \neq 0$, the vectors $\boldsymbol{x}_1, \ldots, \boldsymbol{x}_k$ are linearly dependent. If only the trivial solution exists, i.e., $\lambda_1=\ldots=\lambda_k=0$ the vectors $\boldsymbol{x}_1, \ldots, \boldsymbol{x}_k$ are linearly independent.

Linear independence is one of the most important concepts in linear algebra. Intuitively, a set of linearly independent vectors consists of vectors that have no redundancy, i.e., if we remove any of those vectors from the set, we will lose something.

### Useful properties to determine linear independence
1) vectors are either dependent or independent
2) if one vector in a matrix is $0$ then the vectors are dependent
3) Vectors are linearly dependent if one is a combination of the other
4) Gaussian Elimination is a good way to check dependency
	1) The pivot columns indicate the vectors, linearly independent of the vectors on the left.
	2) The non-pivot columns can be expressed as linear combinations of the pivot columns on their left.

$$
\left[\begin{array}{lll}
1 & 3 & 0 \\
0 & 0 & 2
\end{array}\right]
$$
> All column vectors are linearly independent if and only if all columns are pivot columns. If there is at least one non-pivot column, the columns (and, therefore, the corresponding vectors) are linearly dependent. (Deisenroth et al., 2020, p. 42)

## Notation Trick:
> [!Remark]+
> Remark. Consider a vector space $V$ with $k$ linearly independent vectors $\boldsymbol{b}_1, \ldots, \boldsymbol{b}_k$ and $m$ linear combinations
> $$
> \begin{gathered}
> \boldsymbol{x}_1=\sum_{i=1}^k \lambda_{i 1} \boldsymbol{b}_i, \\
> \vdots \\
> \boldsymbol{x}_m=\sum_{i=1}^k \lambda_{i m} \boldsymbol{b}_i .
> \end{gathered}
> $$
> 
> Defining $\boldsymbol{B}=\left[\boldsymbol{b}_1, \ldots, \boldsymbol{b}_k\right]$ as the matrix whose columns are the linearly independent vectors $\boldsymbol{b}_1, \ldots, \boldsymbol{b}_k$, we can write
> $$
> \boldsymbol{x}_j=\boldsymbol{B} \boldsymbol{\lambda}_j, \quad \boldsymbol{\lambda}_j=\left[\begin{array}{c}
> \lambda_{1 j} \\
> \vdots \\
> \lambda_{k j}
> \end{array}\right], \quad j=1, \ldots, m,
> $$
> in a more compact form.
> We want to test whether $\boldsymbol{x}_1, \ldots, \boldsymbol{x}_m$ are linearly independent. For this purpose, we follow the general approach of testing when $\sum_{j=1}^m \psi_j \boldsymbol{x}_j=\mathbf{0}$. With (2.71), we obtain
> $$
> \sum_{j=1}^m \psi_j \boldsymbol{x}_j=\sum_{j=1}^m \psi_j \boldsymbol{B} \boldsymbol{\lambda}_j=\boldsymbol{B} \sum_{j=1}^m \psi_j \boldsymbol{\lambda}_j
> $$
> 
> This means that $\left\{\boldsymbol{x}_1, \ldots, \boldsymbol{x}_m\right\}$ are linearly independent if and only if the column vectors $\left\{\boldsymbol{\lambda}_1, \ldots, \boldsymbol{\lambda}_m\right\}$ are linearly independent.

## Basis and Rank
Consider a vector space $$
(\mathcal{V},+, \cdot)
$$
and a set of vectors $\mathcal{A}=\{x_{1}, x_{2},\dots, x_{n}\} \subseteq (\mathcal{V},+, \cdot)$. If every vector $\operatorname{v} \in \mathcal{V}$ can be expressed as a linear combination of $\{x_{1}, x_{2},\dots, x_{n}\}$, $\mathcal{A}$ is called a __generating set__ of $\mathcal{V}$. The set of all linear combinations of vectors in $\mathcal{A}$ is called the __span__. 

The notation for a vectors space is
$$
V=\operatorname{span}[\mathcal{A}]
$$
Generating sets are sets of vectors that span vector (sub)spaces, i.e., every vector can be represented as a linear combination of the vectors in the generating set. 


__Basis__. Consider a vector space $V=(\mathcal{V},+, \cdot)$ and $\mathcal{A} \subseteq$ $\mathcal{V}$. A generating set $\mathcal{A}$ of $V$ is called minimal if there exists no smaller set $\tilde{\mathcal{A}} \subsetneq \mathcal{A} \subseteq \mathcal{V}$ that spans $V$. Every linearly independent generating set of $V$ is minimal and is called a basis of $V$.

### Example $\mathbb{R}^3$
The vectors $x_1 = [1, 0, 0]^{T}$, $x_2 = [0, 1, 0]^{T}$, $x_3 = [0, 0, 1]^{T}$, span the three dimensional space and are hence basis vectors for $\mathbb{R}^3$. 

<mark class="hltr-red">NOTE</mark>: the columns are linearly independent ([[Linear Algebra#Linear Independence]] above for more information on linear independence.)

### Properties of a Basis
Let $V=(\mathcal{V},+, \cdot)$ be a vector space and $\mathcal{B} \subseteq \mathcal{V}, \mathcal{B} \neq \emptyset$. Then, the following statements are equivalent:
- Every $V$ possess at least 1 basis, more than one are possible
- $\mathcal{B}$ is a basis of $V$.
- $\mathcal{B}$ is a minimal generating set.
- $\mathcal{B}$ is a maximal linearly independent set of vectors in $V$, i.e., adding any other vector to this set will make it linearly dependent.
- Every vector $\boldsymbol{x} \in V$ is a linear combination of vectors from $\mathcal{B}$, and every linear combination is unique, i.e., with
$$
\boldsymbol{x}=\sum_{i=1}^k \lambda_i \boldsymbol{b}_i=\sum_{i=1}^k \psi_i \boldsymbol{b}_i
$$
and $\lambda_i, \psi_i \in \mathbb{R}, \boldsymbol{b}_i \in \mathcal{B}$ it follows that $\lambda_i=\psi_i, i=1, \ldots, k$.

>[!Example]
> Example 2.16
> - In $\mathbb{R}^3$, the canonical/standard basis is
> $$
> \mathcal{B}=\left\{\left[\begin{array}{l}
> 1 \\
> 0 \\
> 0
> \end{array}\right],\left[\begin{array}{l}
> 0 \\
> 1 \\
> 0
> \end{array}\right],\left[\begin{array}{l}
> 0 \\
> 0 \\
> 1
> \end{array}\right]\right\}
> $$
> - Different bases in $\mathbb{R}^3$ are
> $$
> \mathcal{B}_1=\left\{\left[\begin{array}{l}
> 1 \\
> 0 \\
> 0
> \end{array}\right],\left[\begin{array}{l}
> 1 \\
> 1 \\
> 0
> \end{array}\right],\left[\begin{array}{l}
> 1 \\
> 1 \\
> 1
> \end{array}\right]\right\}, \mathcal{B}_2=\left\{\left[\begin{array}{l}
> 0.5 \\
> 0.8 \\
> 0.4
> \end{array}\right],\left[\begin{array}{l}
> 1.8 \\
> 0.3 \\
> 0.3
> \end{array}\right],\left[\begin{array}{c}
> -2.2 \\
> -1.3 \\
> 3.5
> \end{array}\right]\right\} .
> $$
> - The set
> $$
> \mathcal{A}=\left\{\left[\begin{array}{l}
> 1 \\
> 2 \\
> 3 \\
> 4
> \end{array}\right],\left[\begin{array}{c}
> 2 \\
> -1 \\
> 0 \\
> 2
> \end{array}\right],\left[\begin{array}{c}
> 1 \\
> 1 \\
> 0 \\
> -4
> \end{array}\right]\right\}
> $$
> is linearly independent, but not a generating set (and no basis) of $\mathbb{R}^4$ : For instance, the vector $[1,0,0,0]^{\top}$ cannot be obtained by a linear combination of elements in $\mathcal{A}$.

### Dimensions
__Dimensions__. If $U \subseteq V$ is a subspace of $V$, then $\operatorname{dim}(U) \leqslant \operatorname{dim}(V)$ and $\operatorname{dim}(U)= \operatorname{dim}(V)$ if and only if $U=V$. Intuitively, the dimension of a vector space can be thought of as the number of independent directions in this vector space.

### Rules for Determining a Basis 
The following rules allow the determination of a Basis:
1. Write the spanning vectors as columns of a matrix $A$
2. Determine the row-echelon form of $\boldsymbol{A}$.
3. The spanning vectors associated with the pivot columns are a basis of $U$.

## Rank
> [!Define]
> The number of linearly independent columns of a matrix $A \in \mathbb{R}^{m \times n}$ equals the number of linearly independent rows and is called the rank of $\boldsymbol{A}$ and is denoted by $\operatorname{rk}(\boldsymbol{A})$.

### Properties of Rank
The rank of a matrix has some important properties:
- $\operatorname{rk}(\boldsymbol{A})=\operatorname{rk}\left(\boldsymbol{A}^{\top}\right)$, i.e., the column rank equals the row rank.
- The columns of $\boldsymbol{A} \in \mathbb{R}^{m \times n}$ span a subspace $U \subseteq \mathbb{R}^m$ with $\operatorname{dim}(U)=$ $\operatorname{rk}(\boldsymbol{A})$. Later we will call this subspace the image or range. A basis of $U$ can be found by applying Gaussian elimination to $A$ to identify the pivot columns. `// The column space has a basis`
- The rows of $\boldsymbol{A} \in \mathbb{R}^{m \times n}$ span a subspace $W \subseteq \mathbb{R}^n$ with $\operatorname{dim}(W)=$ $\operatorname{rk}(\boldsymbol{A})$. A basis of $W$ can be found by applying Gaussian elimination to $\boldsymbol{A}^{\top}$. `\\ The row space has also a basis`
- For all $\boldsymbol{A} \in \mathbb{R}^{n \times n}$ it holds that $\boldsymbol{A}$ is regular (invertible) if and only if $\operatorname{rk}(\boldsymbol{A})=n$. 
- For all $\boldsymbol{A} \in \mathbb{R}^{m \times n}$ and all $\boldsymbol{b} \in \mathbb{R}^m$ it holds that the linear equation system $\boldsymbol{A x}=\boldsymbol{b}$ can be solved if and only if $\operatorname{rk}(\boldsymbol{A})=\operatorname{rk}(\boldsymbol{A} \mid \boldsymbol{b})$, where $\boldsymbol{A} \mid \boldsymbol{b}$ denotes the augmented system.
- For $\boldsymbol{A} \in \mathbb{R}^{m \times n}$ the subspace of solutions for $\boldsymbol{A x}=\mathbf{0}$ possesses dimension $n-\operatorname{rk}(\boldsymbol{A})$. `// This will be referred to as the kernel or the null space.`
- A matrix $\boldsymbol{A} \in \mathbb{R}^{m \times n}$ has full rank if its rank equals the largest possible rank for a matrix of the same dimensions. This means that the rank of a full-rank matrix is the lesser of the number of rows and columns, i.e., $\operatorname{rk}(\boldsymbol{A})=\min (m, n)$. A matrix is said to be rank deficient if it does not have full rank.


## Linear Mappings 
A mapping is some transformation of the underlying vectors. Examples are addition or scalar multiplication (inner and outer operation).

Consider two real vector spaces $V, W$. A mapping $\Phi: V \rightarrow W$ preserves the structure of the vector space if
$$
\begin{aligned}
\Phi(\boldsymbol{x}+\boldsymbol{y}) & =\Phi(\boldsymbol{x})+\Phi(\boldsymbol{y}) \\
\Phi(\lambda \boldsymbol{x}) & =\lambda \Phi(\boldsymbol{x})
\end{aligned}
$$
`Note: its just distributivity and associativity`

for all $x, y \in V$ and $\lambda \in \mathbb{R}$. We can summarise this in the following definition:

__Linear Mapping__. For vector space $V,W$ a mapping $\Phi: V \to W$ is called a linear mapping or vector space homomorphism/ linear transformation if:

$$
\forall \boldsymbol{x},\boldsymbol{y} \in V; \forall \lambda, \psi \in \mathbb{R}: \Phi(\lambda \boldsymbol{x}+ \psi \boldsymbol{y})= \lambda \Phi(\boldsymbol{x}) + \psi \Phi (\boldsymbol{y}) 
$$

`\\ Note all linear transformations are matricies, or a matrix is basically a linear transformation. This becomes very important in` [[Matrix Decomposition]] `with single value decomposition and Eigenvalue Decomposition. `

__Injective, Surjective and Bijective__. Consider a mapping $\Phi: V \to W$. Then $\Phi$ is called:

1) Injective: if $\forall \boldsymbol{x}, \boldsymbol{y} \in \mathcal{V}: \Phi(\boldsymbol{x}) = \Phi (\boldsymbol{y}) \Longrightarrow \boldsymbol{x} = \boldsymbol{y}$ <mark class="hltr-orange">FIXME</mark> `// meaning that different inputs lead to different outputs`
2) Surjective: if $\Phi(\mathcal{V})=\mathcal{W}$ `\\ meaning all elements in W can be reached from V`
3) Bijective: if it is Injective and Surjective

![[injective_surjective.png]]

<mark class="hltr-red">NOTE</mark>: A bijective linear mapping can be undone with the inverse $\Phi^{-1}$. 

--- 
__Iso-, Endo-, Automorphism__. The definitions for Iso-, Endo-, Automorphism are as follows:

- Isomorphism: $\Phi: V \to W$ linear and bijective 

A linear map $T$ is called an isomorphism if the following two conditions are satisfied.
- $T$ is one to one. That is, if $T(\vec{x})=T(\vec{y})$, then $\vec{x}=\vec{y}$.
- $T$ is onto. That is, if $\vec{w} \in W$, there exists $\vec{v} \in V$ such that $T(\vec{v})=\vec{w}$.

Two such subspaces which have an isomorphism as described above are said to be isomorphic. 

`Note: example calculation: `
https://math.libretexts.org/Courses/Lake_Tahoe_Community_College/A_First_Course_in_Linear_Algebra_(Kuttler)/05%3A_Linear_Transformations/5.06%3A_Isomorphisms


- Endomorphism: $\Phi: V \to W$ linear <mark class="hltr-orange">FIXME</mark>`\\ linear only means addition???
- Automorphism $\Phi: V \to V$ linear and bijective
- $\operatorname{id}_{V}: V \to V, x \to x$ as the identity mapping or identity automorphism in $V$.


> [!Theorem]
> _Finite-dimensional vector spaces $\mathcal{V}$ and $\mathcal{W}$_ are isomorphic if and only if $\operatorname{Dim}(V)=\operatorname{Dim}(W)$. Intuitively, this means that vector spaces of the same dimension are kind of the same thing, as they can be transformed into each other without incurring any loss.

This implies two things: 
1) Linear mappings of X to Y and Y to W mean that X to W is also linear. 
2) If $\Phi: V \to V$ is an isomorphism then $\Phi^{-1}$ is also an isomorphism. 
3) if $\Phi: V \to V$ is linear and $\Psi: V \to V$ is also linear, the $\Phi+\Psi$ is also linear

### Matrix Representation of Linear Mappings
`Note: A mapping` $𝑇:𝑉→𝑊$ `is called a linear transformation or linear map if it preserves the algebraic operations of addition and scalar multiplication`
$$
T(a \vec{x}+b \vec{y})=a T(\vec{x})+b T(\vec{y})
$$

> [!Define]
> Definition 2.18 (Coordinates). Consider a vector space $V$ and an ordered basis $B=\left(\boldsymbol{b}_1, \ldots, \boldsymbol{b}_n\right)$ of $V$. For any $\boldsymbol{x} \in V$ we obtain a unique representation (linear combination)
> $$
> \boldsymbol{x}=\alpha_1 \boldsymbol{b}_1+\ldots+\alpha_n \boldsymbol{b}_n
> $$
> of $\boldsymbol{x}$ with respect to $B$. Then $\alpha_1, \ldots, \alpha_n$ are the coordinates of $\boldsymbol{x}$ with respect to $B$, and the vector
> $$
> \boldsymbol{\alpha}=\left[\begin{array}{c}
> \alpha_1 \\
> \vdots \\
> \alpha_n
> \end{array}\right] \in \mathbb{R}^n
> $$
> is the coordinate vector/coordinate representation of $\boldsymbol{x}$ with respect to the ordered basis $B$.

A basis spans a coordinate system (most notably, the Cartesian coord system spanned by [0,1] and [1,0]). However, any basis can form a valid coordinate system.

**Transformation matrices allow for the mapping of coordinates wrt. one basis to another coordinate system wrt. another basis.** This is given by: 
$$
\Phi\left(\boldsymbol{b}_j\right)=\alpha_{1 j} \boldsymbol{c}_1+\cdots+\alpha_{m j} \boldsymbol{c}_m=\sum_{i=1}^m \alpha_{i j} \boldsymbol{c}_i
$$
If $\hat{x}$ is the coordinate vector of $x \in V$ with respect to $B$ and $\hat{y}$ the coordinate vector of $\boldsymbol{y}=\Phi(x) \in W$ with respect to $C$, then
$$
\hat{\boldsymbol{y}}=\boldsymbol{A}_{\Phi} \hat{\boldsymbol{x}}
$$

### Basis Change
In the following, we will have a closer look at how transformation matrices of a linear mapping $\Phi: V \rightarrow W$ change if we change the bases in $V$ and $W$. Consider two ordered bases
$$
B=\left(\boldsymbol{b}_1, \ldots, \boldsymbol{b}_n\right), \quad \tilde{B}=\left(\tilde{\boldsymbol{b}}_1, \ldots, \tilde{\boldsymbol{b}}_n\right)
$$
of $V$ and two ordered bases
$$
C=\left(\boldsymbol{c}_1, \ldots, \boldsymbol{c}_m\right), \quad \tilde{C}=\left(\tilde{\boldsymbol{c}}_1, \ldots, \tilde{\boldsymbol{c}}_m\right)
$$
of $W$. 

Moreover, $\boldsymbol{A}_{\Phi} \in \mathbb{R}^{m \times n}$ is the transformation matrix of the linear mapping $\Phi: V \rightarrow W$ with respect to the bases $B$ and $C$, and $\tilde{A}_{\Phi} \in \mathbb{R}^{m \times n}$ is the corresponding transformation mapping with respect to $\tilde{B}$ and $\tilde{C}$. 

In the following, we will investigate how $\boldsymbol{A}$ and $\tilde{\boldsymbol{A}}$ are related, i.e., how/ whether we can transform $\boldsymbol{A}_{\Phi}$ into $\tilde{\boldsymbol{A}}_{\Phi}$ if we choose to perform a basis change from $B, C$ to $\tilde{B}, \tilde{C}$.

To perform a basis change we can use the following transformation:
$$
\tilde{A}_{\Phi}=T^{-1} A_{\Phi} S
$$
where $S$ is the transformation matrix that maps coordinates with respect to $\tilde{B}$ onto $B$ and $T$ is the transformation matrix that maps coordinates wrt. $\tilde{C}$ onto $C$.
With a basis change in $V$ ( $B$ is replaced with $\tilde{B})$ and $W\left(C\right.$ is replaced with $\tilde{C}$ ), the transformation matrix $\boldsymbol{A}_{\Phi}$ of a linear mapping $\Phi: V \rightarrow W$ is replaced by an equivalent matrix $\tilde{\boldsymbol{A}}_{\Phi}$ with
$$
\tilde{A}_{\Phi}=\boldsymbol{T}^{-1} \boldsymbol{A}_{\Phi} S
$$

> [!Define]
> Definition 2.21 (Equivalence). Two matrices $\boldsymbol{A}, \tilde{A} \in \mathbb{R}^{m \times n}$ are equivalent if there exist regular matrices $S \in \mathbb{R}^{n \times n}$ and $T \in \mathbb{R}^{m \times m}$, such that $\tilde{A}=T^{-1} A S$.
> Definition 2.22 (Similarity). Two matrices $\underset{\sim}{\boldsymbol{A}}, \tilde{\boldsymbol{A}} \in \mathbb{R}^{n \times n}$ are similar if there exists a regular matrix $S \in \mathbb{R}^{n \times n}$ with $\tilde{A}=S^{-1} A S$
> 
> Remark. Similar matrices are always equivalent. However, equivalent matrices are not necessarily similar.


### Images and Kernels



## Affine Space
$$
\begin{aligned}
L & =x_0+U:=\left\{x_0+\boldsymbol{u}: \boldsymbol{u} \in U\right\} \\
& =\left\{\boldsymbol{v} \in V \mid \exists \boldsymbol{u} \in U: \boldsymbol{v}=x_0+\boldsymbol{u}\right\} \subseteq V
\end{aligned}
$$
Note that the definition of an affine subspace excludes $\mathbf{0}$ if $x_0 \notin U$. Therefore, an affine subspace is not a (linear) subspace (vector subspace) of $V$ for $x_0 \notin U$.

Examples of affine subspaces are points, lines, and planes in $\mathbb{R}^3$, which do not (necessarily) go through the origin.


### Affine Subspaces
see chapter 2.9.1 
### Affine Mappings
see chapter 2.9.2


