---
title: Shallow Neural Networks
date: 31-05-2023
time: 14:35
author: Luca Trautmann
tags: ["ML"]
series: "Machine Learning Fundamentals"
chapter: 5
---

# Shallow Neural Networks
Shallow neural networks are functions that map multivariate inputs $x$ to multivariate outputs $y$.   On a high level, all neural networks are <mark style="background: #FFB8EBA6;">universal function approximations</mark> with certain level of precision (__Universal Approximation Theorem__). The more hidden activation units in the network, the closer the approximation of a continuous function is. 

## Multivariate Inputs and Outputs
The Universal Approximation Theorem also holds for multivariate inputs and outputs. In these cases, the network will map the inputs $[x_1, x_2, x_3, ... , x_N]^T$ to the multivariate output predictions $[y_1, y_2, y_3, ... ,y_n]$. The general principle is the same as for simple functions with one input and one output. In 2D any continuous function plane will be approximated with piecewise linear polygonal regions. In higher dimensions this becomes difficult to picture but the general principle still holds - <mark style="background: #FFB8EBA6;">higher dimensional functions are being approximated with linear combinations of polytopes in the multidimensional input space</mark>.

## Shallow Neural Networks: General Case
To describe a general case for shallow neural networks, it is necessary to generalise the formula for the hidden units in the networks and the combination of these hidden networks. In general, shallow neural networks take a multidimensional input space $x \in \mathbb{R}^{D_i}$ with $D_i$ being the dimension of the input to a multidimensional output $y \in \mathbb{R}^{D_o}$ with $D_o$ being the output dimensions. For the hidden unit (node) we end up with the following equation: 
$$h_d = a \left [ \theta_{d0} + \sum^{D_i}_{i=1}\theta_{di}x_i\right]$$
where $a$ is the activation function (e.g. ReLU) and $\sum^{D_i}_{i=1}\theta_{di}x_i$ is a weighted sum of the inputs and their corresponding coefficients. 

> [!Activation Function Note]+
> The activation function permits the model to describe nonlinear relations between input and the output, and as such, it must be nonlinear itself; with no activation function, or a linear activation function, the overall mapping from input to output would be restricted to be linear. With ReLU activations, the network divides the input space into convex polytopes defined by the intersections of hyperplanes computed by the “joints” in the ReLU functions. Each convex polytope contains a different linear function.

The output $y$ is then described with the following function: 
$$\begin{aligned} y &= \phi_{j0} + \sum^D_{d=1} \phi_{jd}h_d \\
y &= \phi_{j0} + \sum^D_{d=1} \phi_{jd} \left [ \theta_{d0} + \sum^{D_i}_{i=1}\theta_{di}x_i\right] \quad \text{with}\,h_d = \phi_{j0} + \sum^D_{d=1} \phi_{jd}h_d 
\end{aligned}$$
Here, the output $y$ is a weighted sum of the activations $h$ and a general offsetting term (bias). 
![[shallow_nn.svg#invert]]
# Series
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```
