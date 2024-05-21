---
title: PT Basic Concepts
date: 06-02-2024
time: 15:18
author: Luca Trautmann
tags: 
series: PT
chapter: 1
modified: 2024-02-09
---
# PT Basic Concepts
## Probability and Relative Frequency
Roughly speaking, the probability P(A) of the event A equals the fraction of experiments leading to the occurrence of A in a large series of trials; also known as the __relative frequency__. In the long-run, for large number of experiments, the relative frequency will cluster around a value. 

$$
\mathbf{P}(A) \sim \frac{n(A)}{n}
$$

And so, in  the frequency or frequentist reading of probability, we assume that a "probability" is the long-run frequency of an random event if the number of trial tends against infinity. Given by: 

$$\mathbf{P}(A)=\lim _{n \rightarrow \infty} \frac{n(A)}{n}$$

## Rudiments of Combinatorial Analysis
THEOREM 1.1: _Given $n_1$ elements $a_1, a_2, ... ,a_n$ and $n_2$ elements $b_1, b_2, ... ,b_n$, there are precisely $n_1n_2$ distinct ordered pairs $(a_i, b_j)$ containing one element of each kind. 

![[Combinatorics.png#invert]]

Proof. Represent the elements of the first kind by points of the x-axis, and those of the second kind by points of the y-axis. Then the possible pairs (ai, b1) are points of a rectangular lattice in the xy-plane. $\square$ 

This Theorem is extendable into $n_r$ dimensions, by means of mathematical induction:

THEOREM 1.2. Given $n_1$ elements $a_1, a_2, \ldots, a_{n_1}, n_2$ elements $b_1$, $b_2, \ldots, b_{n_2}$, etc., up to $n_r$ elements $x_1, x_2, \ldots, x_{n_r}$, there are precisely $n_1 n_2 \cdots n_r$ distinct ordered r-tuples $\left(a_{i_1}, b_{i_2}, \ldots, x_{i_r}\right)$ containing one element of each kind.?

Proof. For $r=2$, the theorem reduces to Theorem 1.1. Suppose the theorem holds for $r-1$, so that in particular there are precisely $n_2 \cdots n_r$ $(r-1)$-tuples $\left(b_{i_2}, \ldots, x_{i_r}\right)$ containing one element of each kind. Then, regarding the $(r-1)$-tuples as elements of a new kind, we note that each $r$-tuple $\left(a_{i_1}, b_{i_2}, \ldots, x_{i_r}\right)$ can be regarded as made up of a $(r-1)$-tuple $\left(b_{i_2}, \ldots, x_{i_r}\right)$ and an element $a_{i_1}$. Hence, by Theorem 1.1 , there are precisely
$$
n_1\left(n_2 \cdots n_r\right)=n_1 n_2 \cdots n_r
$$
$r$-tuples containing one element of each kind. 
### Example I: Casting the Die
_What is the probability of getting three sixes in a throw of three dice?_

Each die can be represented one dimension in a tensor of three-valued tuples. This follows 1.2 and hence we now know that there are 6 * 6 * 6 possible combinations. The solution 6, 6, 6, can only occur once, hence the solution based on combinatorics is $$\frac{1}{216}$$

### Example II: Sampling with Replacement
With replacement following THEOREM 1.2 there are 
$$
N= n^r
$$
tuples possible. 

In the context of [[Combinatorics.png]] seen above, this will just be a r-dimensional tensor. 

### Example III: Sampling with Replacement
Sampling without replacement leads to a smaller set of values for each trial. So 
$$
N=n-r+1
$$
distinct samples. 

> FIXME There is an relationship to infinite series that I still need to be investigated.

THEOREM 1.3: _A population of n elements has precisely_
$$C_r^n=\frac{n !}{r !(n-r) !}$$
_subpopulations of size $r \leq n$_

