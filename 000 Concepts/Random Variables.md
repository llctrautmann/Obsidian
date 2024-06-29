---
title: Random Variables
date:
  - 19-05-2023
time: 16:55
author: Luca Trautmann
tags:
  - ProbTheory
series: Probability Theory
chapter: 2
modified: 2024-06-29
formula: 
Docstring:
  - A random variable is a mathematical concept used in probability theory and statistics to represent the outcomes of a random process or experiment. It is a variable whose value is determined by chance, and can take on a range of possible values with different probabilities.
aliases:
  - random variable
  - RVs
---

# Definition
- A random variable is a mathematical concept used in probability theory and statistics to represent the outcomes of a random process or experiment. 
- It is a variable whose value is determined by chance, and can take on a range of possible values with different probabilities. 
- Random variables can be discrete or continuous, depending on whether their possible values are countable or uncountable. 

For example $x = 7$ is not a random variable. However, the outcome of a dice roll is a random variable (i.e. it contains randomness and is not fixed). All the possible outcomes of the random variable are called the sample space. A random variable can take any value in the sample space. All the possibilites in the sample space are events (e.g. for a dice roll, the dice can land in 6 positions, hence there are six events):
$$S = \{1,2,3,4,5,6\}$$
Each event in the sample space have an associated probability. For example with an unbiased dice the probability for throwing a 1 is:
$$P(X= 1) = \frac{1}{6}$$
## Discrete Random Variables
- If the sample space is finite or countable, then $X$ is called a discrete RV. The event $x$ and its corresponding probability are defined as:
$$P(X=x) = \text{value}$$
- The probability mass function is a mapping from the possible values of the random variable to its probabilities.
$$p(x) = P(X=x)$$

### Probability Mass Function
A probability mass function is used to describe the probability distribution of a discrete random variable, which can only take on a finite or countably infinite number of values. The PMF gives the probability of the random variable taking on each possible value, and the sum of all probabilities is equal to 1. 


## Continuous Random Variable
- If the sample space is not finite and countable the random variable will be continuous it will be called a continuous RV. 
	- requires integration ($\int$) to get the corresponding probabilities.

- Instead of singular events having occurring with a probability, intervals over ranges of values determine the probability. 

- The probability for a specific value to occur is always 0.

- Probability distributions for continuous random variables are described using probability density functions which represent the likelihood of a variable taking on a specific value. The area under the PDF curve represents the probability of the variable being within a certain range of values.

### Cumulative Distribution Function
The cumulative distribution over the random variable $X$ is defined as a monotonically increasing function:

$$\large\tag{6}P(x) = P(X \leq x)$$
So we can define the probability of $X$ being between $a$ and $b$ as:

$$\large\tag{7}P(a \leq X \leq b) = P(b) - P(a)$$


### Probability Density Function
The Probability Density Function (PDF) represents the relative likelihood for a continuous random variable to take on a given value. The key concept of PDF is density rather than probability. The value of the PDF at any two different sample points can be different and may not equal the probability of obtaining those sample points.

Given that it’s a continuous random variable, the probability of the variable taking on any specific value is technically 0, since there are an infinite number of possible values. Instead, the value of the PDF at two different points can be used to compute the probability of falling within a certain range of values. Mathematically, the PDF is defined as the derivative of the CDF. Hence:

$$p(x) = \frac{d}{dx}P(x)$$
From the PDF we can calculate the probability of an event in within a range of the sample space as:

$$P(a \leq X \leq b) = \int^b_ap(x)dx = P(b) - P(a)$$
Intuitively, this says the probability of X being in a small interval around x is the density at x times the width of the interval. To visualize, consider the PDF of a standard normal distribution. The PDF of a standard normal distribution is given by:

$$\large\tag{2}
\mathcal{N}\left(y \mid \mu, \sigma^2\right) \triangleq \frac{1}{\sqrt{2 \pi \sigma^2}} e^{-\frac{1}{2 \sigma^2}(y-\mu)^2}$$

Now suppose we want to find the probability of the random variable falling between -1 and 1. This would be represented by the area under the PDF curve between -1 and 1 and would be computed as:

$$P(-1 \leq X \leq 1) = \int^1_{-1}f(x)dx = P(1) - P(-1)$$



