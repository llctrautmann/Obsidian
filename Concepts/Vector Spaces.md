---
title: Vector Spaces
date:
  - 03-05-2024
time: 17:54
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
chapter: 0
status: Incomplete
modified: 2024-05-17
formula: $(\mathcal{V},+, \cdot)$
---
# Vector Spaces
This abbreviation contains the condensed information about vector spaces. 

$$\large\tag{1}
(\mathcal{V},+, \cdot)
$$


$(\mathcal{V},+, \cdot)$

`Remember: Addition and Scalar Multiplication are the most important tenets of vector spaces.`


## Vector Spaces Basics
This is a vector:
$$
\mathbf{x}=\left[\begin{array}{c}
x_1 \\
x_2 \\
\vdots \\
x_n 
\end{array}\right]
$$

a vector in $\mathbb{R}^3$ looks like this

$$\mathbf{x}=\left[\begin{array}{c}
1 \\
2 \\
3
\end{array}\right]$$

a vector in $\mathbb{R}^5$ looks like this

$$\mathbf{x}=\left[\begin{array}{c}
1 \\
2 \\
3 \\  
4 \\
5 \\
\end{array}\right]$$

## Main Operations
The two main operations for every vector space are:

- addition
- scalar multiplication

Both are defined element-wise:

$$\large
\mathbf{x}+\mathbf{y}=\left[\begin{array}{c}
x_1+y_1 \\
\vdots \\
x_n+y_n
\end{array}\right], \quad \alpha \mathbf{x}=\left[\begin{array}{c}
\alpha x_1 \\
\vdots \\
\alpha x_n
\end{array}\right]
$$

## Conditions
There are six necessary conditions a vector space needs to conform to:

### Additive Identity
Every vector space needs to include $\large\mathbf{0}$ / the origin. For all $\mathbf{x}\in V$ it must be possible to do: 

$$\mathbf{x}+\mathbf{0}=\mathbf{x}$$


### Additive Inverse
There needs to exist an inverse element $-\mathbf{x}$ so that 

$$
\mathbf{x} + (-\mathbf{x})=\mathbf{0}
$$

### Multiplicative Identity
There exists a multiplicative identity in $\mathbb{R}$, that allows for all $\mathbf{x} \in V$

$$
1\mathbf{x} = \mathbf{x}
$$

This is in most cases the [[Matrix Definitions#Identity Matrix]]. And trivially in Calculus that is 1. 

`This also neatly shows that there is no difference between the single dimensional math and the higher dimensional math.`

### Commutativity
Same definition as commutativity in any other algebra.
For all $\mathbf{x}, \mathbf{y} \in V$

$$
\mathbf{x}+\mathbf{y}=\mathbf{y}+\mathbf{x}
$$


### Associativity
For all $\mathbf{x}, \mathbf{y}, \mathbf{z} \in V$ and $\alpha, \beta \in \mathbb{R}$ 

$$
(\mathbf{x}+\mathbf{y})+\mathbf{z}=\mathbf{x}+(\mathbf{y}+\mathbf{z})
$$
$$
\alpha(\beta \mathbf{x})=(\alpha \beta) \mathbf{x}
$$


### Distributivity
For all $\mathbf{x}, \mathbf{y}, \mathbf{z} \in V$ and $\alpha, \beta \in \mathbb{R}$ 

$$\alpha (\mathbf{x + \mathbf{y}})= \alpha \mathbf{x} + \alpha \mathbf{y}$$
$$
(\alpha+\beta) \mathbf{x}=\alpha \mathbf{x}+\beta \mathbf{x}
$$



## Relevant Mathematical Background 
Generally, Vector spaces are an extension of [[Groups]] and related to Set Theory. A group is a set of elements with operations defined on the elements (see [[Groups#Conditions]]).  

With the basics idea of [[Groups]] in mind, a vector space is functionally a special group with its elements being vectors and the two defined operations

1)  $+: \mathcal{V} \times \mathcal{V} \rightarrow \mathcal{V}$ (inner operation)
2)  $\cdot: \mathbb{R} \times \mathcal{V} \rightarrow \mathcal{V}$ (outer operation)

And all other remaining conditions as outlined above. 

This abbreviation contains the condensed information about vector spaces. 

$$\large\tag{1}
(\mathcal{V},+, \cdot)
$$

`Remember: Addition and Scalar Multiplication are the most important tenets of vector spaces.`



## Relevant Literature

> [!PDF|yellow] [[Thomas2018.pdf#page=6&selection=15,55,31,0&color=yellow|@Thomas2018, p.6]]
> A vector space V is a set (the elements of which are called vectors) on which two operations are defined: vectors can be added together, and vectors can be multiplied by real numbers called scalars.

> [!PDF|yellow] [[deisenroth2020.pdf#page=43&selection=80,0,118,56&color=yellow|deisenroth2020, p.37]]
> > When we discussed groups, we looked at sets G and inner operations on $\mathcal{G}$, i.e., mappings $\mathcal{G} × \mathcal{G} → \mathcal{G}$ that only operate on elements in $\mathcal{G}$. In the following, we will consider sets that in addition to an inner operation $+$ also contain an outer operation $·$, the multiplication of a vector $x \in \mathcal{G}$ by a scalar $\lambda \in \mathbb{R}$. We can think of the inner operation as a form of addition, and the outer operation as a form of scaling. Note that the inner/outer operations have nothing to do with inner/outer products.


## Relevant Notes
- [[Concepts/Linear Algebra]]
- [[Linear Algebra Foundation]]
- 