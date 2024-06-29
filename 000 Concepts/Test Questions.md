---
modified: 2024-06-29
---

# What is the sample space $\Omega$ in probability theory?

The sample space $\Omega$ is the set of all possible outcomes of a random experiment.



# Define a random variable.

A random variable $X$ is a measurable function from the sample space $\Omega$ to the real numbers $\mathbb{R}$.



# What is the range of a probability measure $\mathbb{P}$?

The range of a probability measure $\mathbb{P}$ is $[0, 1]$, meaning it assigns a probability between 0 and 1 to each event in the $\sigma$-algebra $\mathcal{F}$.



# What does it mean for an event to be measurable?

An event is measurable if it belongs to the $\sigma$-algebra $\mathcal{F}$, meaning we can assign a probability to it using the probability measure $\mathbb{P}$.



# State the law of total probability.

The law of total probability states that if $\{B_i\}$ is a partition of the sample space $\Omega$ (i.e., disjoint events whose union is $\Omega$), then for any event $A$:
$$
\mathbb{P}(A) = \sum_{i} \mathbb{P}(A \cap B_i)
$$



# What is a mutually exclusive event?

Two events $A$ and $B$ are mutually exclusive if $A \cap B = \emptyset$, meaning they cannot occur simultaneously.



# Define conditional probability.

Conditional probability of an event $A$ given an event $B$ is defined as:
$$
\mathbb{P}(A \mid B) = \frac{\mathbb{P}(A \cap B)}{\mathbb{P}(B)}
$$
provided that $\mathbb{P}(B) > 0$.



# What is the expected value of a random variable $X$?

The expected value (or mean) of a random variable $X$, denoted $\mathbb{E}[X]$, is the sum or integral of $X$ weighted by its probability:
$$
\mathbb{E}[X] = \sum_{i} x_i \mathbb{P}(X = x_i) \quad \text{(discrete)}
$$
$$
\mathbb{E}[X] = \int_{-\infty}^{\infty} x f_X(x) \, dx \quad \text{(continuous)}
$$



# State the law of large numbers.

The law of large numbers states that as the number of trials $n$ increases, the sample average of the results will converge to the expected value of the random variable:
$$
\frac{1}{n} \sum_{i=1}^n X_i \xrightarrow{n \to \infty} \mathbb{E}[X]
$$



# What is the variance of a random variable $X$?

The variance of a random variable $X$, denoted $\text{Var}(X)$, measures the dispersion of $X$ around its mean and is defined as:
$$
\text{Var}(X) = \mathbb{E}[(X - \mathbb{E}[X])^2]
$$
