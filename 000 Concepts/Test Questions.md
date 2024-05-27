---
modified: 2024-05-27
---
# What are the two main operations for every vector space?

Addition and scalar multiplication.

# What is the additive identity in a vector space?

The vector $\mathbf{0}$, such that $\mathbf{x} + \mathbf{0} = \mathbf{x}$ for all $\mathbf{x} \in V$.

# What is the additive inverse in a vector space?

For every vector $\mathbf{x}$, there exists an inverse element $-\mathbf{x}$ such that $\mathbf{x} + (-\mathbf{x}) = \mathbf{0}$.

# What is the multiplicative identity in a vector space?

The scalar 1, such that $1\mathbf{x} = \mathbf{x}$ for all $\mathbf{x} \in V$.

# What is the commutativity condition in a vector space?

For all $\mathbf{x}, \mathbf{y} \in V$, $\mathbf{x} + \mathbf{y} = \mathbf{y} + \mathbf{x}$.

# What is the associativity condition in a vector space?

For all $\mathbf{x}, \mathbf{y}, \mathbf{z} \in V$ and $\alpha, \beta \in \mathbb{R}$:
- $(\mathbf{x} + \mathbf{y}) + \mathbf{z} = \mathbf{x} + (\mathbf{y} + \mathbf{z})$
- $\alpha(\beta \mathbf{x}) = (\alpha \beta) \mathbf{x}$

# What is the distributivity condition in a vector space?

For all $\mathbf{x}, \mathbf{y} \in V$ and $\alpha, \beta \in \mathbb{R}$:
- $\alpha (\mathbf{x} + \mathbf{y}) = \alpha \mathbf{x} + \alpha \mathbf{y}$
- $(\alpha + \beta) \mathbf{x} = \alpha \mathbf{x} + \beta \mathbf{x}$

# What is a vector space?

A set $\mathcal{V}$ with two operations defined: vector addition and scalar multiplication, satisfying specific conditions.

# What is a vector in $\mathbb{R}^3$?

A vector in $\mathbb{R}^3$ looks like this:
$$\mathbf{x}=\left[\begin{array}{c}
1 \\
2 \\
3
\end{array}\right]$$

# What is a vector in $\mathbb{R}^5$?

A vector in $\mathbb{R}^5$ looks like this:
$$\mathbf{x}=\left[\begin{array}{c}
1 \\
2 \\
3 \\  
4 \\
5 \\
\end{array}\right]$$

# What are the six necessary conditions a vector space needs to conform to?

1. Additive Identity
2. Additive Inverse
3. Multiplicative Identity
4. Commutativity
5. Associativity
6. Distributivity

# What is the purpose of inner products in linear algebra?

Inner products allow for the introduction of intuitive geometrical concepts, such as the length of a vector and the angle or distance between two vectors.

  

# How are inner products defined in vector spaces?

Inner products are defined as a bilinear mapping from the vector space onto the real line.

  

# What is the generalised inner product function notation?

$$\langle\cdot, \cdot\rangle: V \times V \rightarrow \mathbb{R}$$

  

# What are the fundamental axioms that a bilinear map must adhere to in vector spaces?

Addition and multiplication.

  

# What is the positive-definite condition for inner products?

$$\forall \boldsymbol{x} \in V \backslash\{\mathbf{0}\}: \langle\boldsymbol{x}, \boldsymbol{x}\rangle>0, \quad \langle\boldsymbol{0}, \boldsymbol{0}\rangle=0$$

  

# What is the linearity condition in the first slot for inner products?

$$\langle\mathbf{x}+\mathbf{y}, \mathbf{z}\rangle=\langle\mathbf{x}, \mathbf{z}\rangle+\langle\mathbf{y}, \mathbf{z}\rangle \quad \text{and} \quad \langle\alpha \mathbf{x}, \mathbf{y}\rangle=\alpha\langle\mathbf{x}, \mathbf{y}\rangle$$

  

# What is the symmetry condition for inner products?

$$\langle\mathbf{x}, \mathbf{y}\rangle=\langle\mathbf{y}, \mathbf{x}\rangle$$

  

# What is a special case of a general inner product?

The dot product.

  

# What is the dot product formula?

$$\boldsymbol{x}^{\top} \boldsymbol{y}=\sum_{i=1}^n x_i y_i$$

  

# What is an inner product space?

The pair $(V,\langle\cdot, \cdot\rangle)$ is called an inner product space or (real) vector space with inner product.

  

# What is a Euclidean vector space?

A vector space $(V,\langle\cdot, \cdot\rangle)$ using the dot product.

  

# How do inner products induce norms?

$$\|\mathbf{x}\|=\sqrt{\langle\mathbf{x}, \mathbf{x}\rangle}$$

  

# What is the relationship between inner products, norms, and metrics?

Inner products induce norms, which induce metrics. Therefore, an inner product space is a normed space and a metric space.

  

# What is a major purpose of inner products in vector spaces?

To determine whether vectors are orthogonal to each other.