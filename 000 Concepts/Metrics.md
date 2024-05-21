---
title: Metrics
date:
  - 18-05-2023
time: 15:05
author: Luca Trautmann
tags:
  - "#LinAlg"
series: Linear Algebra
chapter: "1"
modified: 2024-05-18
formula: $$d = \left(\sum_{i=1}^{n}|a_i-b_i|^p\right)^\frac{1}{p}$$
---

# Metrics
A distance function, often simply called a "metric" or a "norm" in the context of vector spaces, must satisfy certain conditions to be considered valid. These properties are as follows: 

1.  **Non-negativity:** The distance between any two points must be greater than or equal to zero ($d(x, y) \geq 0$). In other words, there are no negative distances. When $x=y$, the distance should be zero ($d(x, x) = 0$), which is a particular case of this property.
2.  **Symmetry:** The distance from point $x$ to point $y$ must be the same as the distance from point $y$ to point $x$ ($d(x, y) = d(y, x)$).
3.  **[[Triangle Inequality]]:** The direct distance from point $x$ to point $y$ must be less than or equal to the distance from point $x$ to point $z$ plus the distance from point $z$ to point $y$ ($d(x, y) \leq d(x, z) + d(z, y)$). This is often visualised with the idea that the length of one side of a triangle is always less than or equal to the sum of the lengths of the other two sides.

When these rules are in a vector space, a norm also needs to satisfy:
1.  **Homogeneity (or Scalability):** For any real number $\alpha$ and any vector $v$, the norm of the scalar multiple $\alpha v$ is equal to the absolute value of $\alpha$ times the norm of $v$. Written mathematically, $||\alpha v|| = |\alpha| ||v||$.

These rules ensure that the distance function behaves in a way that matches our intuitive understanding of physical distance, and they allow the function to be used in a wide variety of mathematical and computational applications.


## Distance in One Dimension (1D)

The concept of distance is straightforward in one dimension. Given two real numbers, the distance between them is simply the absolute value of their difference. For instance, for $a = 2$ and $b = 5$, the distance $d$ between them can be calculated as:
$$d = |a - b| = |2 - 5| = 3$$
## Distance in Two Dimensions (2D) and Beyond: Euclidean Distance

The concept of distance extends naturally to two dimensions and beyond. The most common measure of distance in such cases is the Euclidean distance, named after the ancient Greek mathematician Euclid. In two dimensions, the Euclidean distance between points $a = (a_1, a_2)$ and $b = (b_1, b_2)$ is given by:


$$d = \sqrt{(a_1 - b_1)^2 + (a_2 - b_2)^2}
$$

so for the two vectors $\begin{bmatrix} 1 \\ 1 \end{bmatrix}$  and $\begin{bmatrix} 2 \\ 4 \end{bmatrix}$ the result will be: 
$$d = \sqrt{(1-2)^2 + (1-4)^2} = \sqrt{10}$$
This can be generalised to more than two points with the formula:

$$d = \sqrt{\sum_{i=1}^{n}(a_i-b_i)^2}$$
## Other Types of Distances

1. **Manhattan distance (L1):** Given two points $a = (a_1, a_2, ..., a_n)$ and $b = (b_1, b_2, ..., b_n)$, the Manhattan distance is given by:

$$
d = \sum_{i=1}^{n} |a_i-b_i|
$$

2. **Chebyshev distance:** The Chebyshev distance between the same two points is:

$$
d = \max_{i} |a_i-b_i|
$$

3. **Minkowski distance:** The Minkowski distance is a generalisation of both Euclidean and Manhattan distances. It is given by:

$$
d = \left(\sum_{i=1}^{n}|a_i-b_i|^p\right)^\frac{1}{p}
$$


where $p$ is a parameter. When $p=2$, we get the Euclidean distance. When $p=1$, we get the Manhattan distance.

## Distance Between Probability Distributions

1. **[[Kullback-Leibler (KL) divergence]]:** Given two probability distributions $P$ and $Q$ defined over the same random variable, the KL divergence from $P$ to $Q$ is:

$$
D_{KL}(P||Q) = 
\begin{cases} 
\sum_{i} P(i) \log \frac{P(i)}{Q(i)} & \text{if discrete} \\
\int P(x) \log \frac{P(x)}{Q(x)} dx & \text{if continuous}
\end{cases}
$$

2. **Jensen-Shannon (JS) divergence:** The JS divergence is the average of the KL divergence of $P$ from the average distribution $M$, and the KL divergence of $Q$ from $M$. If $P$ and $Q$ are both discrete:

$$
D_{JS}(P||Q) = \frac{1}{2} D_{KL}(P||M) + \frac{1}{2} D_{KL}(Q||M)
$$

where $M = \frac{1}{2}(P + Q)$.

3. **Earth Mover's (EM) distance (Wasserstein distance):** Given two discrete probability distributions $P$ and $Q$, where $P = \{p_1, p_2, ..., p_n\}$ and $Q = \{q_1, q_2, ..., q_n\}$ are sorted in non-decreasing order, the EM distance (also known as 1st Wasserstein distance) between $P$ and $Q$ is:

$$
W(P, Q) = \sum_{i=1}^{n} |F^{-1}(p_i) - F^{-1}(q_i)|
$$

where $F^{-1}$ is the quantile function of the underlying distribution.

4. **Total Variation (TV) distance:** The TV distance between two probability distributions $P$ and $Q$ is defined as:

$$
D_{TV}(P, Q) = \frac{1}{2} \sum_{i} |P(i) - Q(i)|
$$

## Distances in Machine Learning

In machine learning, these distance measures are implicitly used within various algorithms and methods rather than being explicitly calculated as standalone measures. However, here are the basic principles in each case:

1. **Clustering:** In K-means clustering, the objective is to minimise the within-cluster sum of squares (WCSS), equivalent to minimising the sum of Euclidean distances between each point and the centroid of its assigned cluster. DBSCAN clusters point based on density, which is determined by counting the number of points within a certain Euclidean distance of each point.
2. **Classification:** In K-Nearest Neighbors, a new point is classified based on the majority class of its nearest neighbours according to a chosen distance metric (commonly Euclidean).
3. **Dimensionality reduction:** In PCA, the distance is implicitly used to compute the covariance matrix. In t-SNE, a variant of the Kullback-Leibler divergence is used to measure the similarity between the high-dimensional distribution of data points and their low-dimensional counterparts.
4. **Anomaly detection:** Outliers can be identified as points significantly distant from others according to a chosen distance metric (commonly Euclidean). This is often done by computing the distance of each point to its $k$th nearest neighbour and identifying points whose distance is much larger than average as outliers.