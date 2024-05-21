---
title: Interactions between Random Variables
date: 20-05-2023
time: 15:52
author: Luca Trautmann
tags: ["ML"]
series: "Probability Theory"
chapter: 4
---
>[!Rule]+
> There are three fundamental rules that for the basis of all of probability theory:
> 
> __<mark style="background: #FF5582A6;">Instance Rule</mark>__
> $P(A)$ is a continuous monotonic function in $[0, 1]$
> 
> __<mark style="background: #FF5582A6;">Sum Rule</mark>__ 
> For two random variables $X$ and $Y$ the marginal probability of $X$ is the sum of all possible states of $Y$ for $(X = x_1)$ to $(X = x_n)$.
> $$p(X = x) = \sum_yp(X=x, Y=y)$$
> 
> __<mark style="background: #FF5582A6;">Product Rule</mark>__
> Each joint distribution can be written as the product of the event probability and the conditional probability.
> $$p(x,y) = p(x) \times p(y|x)$$
> The product rule can be extended to $D$ dimensions and becomes very important to creating high dimensional joint distributions and is called the <mark style="background: #FF5582A6;">chain Rule</mark>.
> $$\begin{gathered}P\left(A_1, A_2, \ldots, A_N \mid B_{bg}\right)=P\left(A_{1 \mid}A_2, A_3, \ldots, A_N, B_{bg}\right) P\left(A_2 \mid A_3, A_4, \ldots, A_N, B_{bg}\right) \\\cdots P\left(A_N \mid B_{bg}\right)\end{gathered}$$



# Interactions between Random Variables
## Marginal Probabilities:
Marginal probabilities refer to the probabilities of individual events or random variables occurring independently, without considering other variables. They are obtained by summing or integrating the joint probabilities over the other variables.  

The marginal probability of an event A is denoted as P(A) and can be calculated using the formula:
$$P(A) = \sum_{\text{all possible outcomes}} P(A, B)$$
or
$$P(A) = \int_{\text{all possible values}} P(A, B) \, dB$$

> [!Example]-
> __Example Contingency Table__
> $$
> \begin{array}{cccc}
> & Y=0 & Y=1 & P(X) \\ 
> X=0 & P(X=0, Y=0) & P(X=0, Y=1) & P(X=0) \\ 
> X=1 & P(X=1, Y=0) & P(X=1, Y=1) & P(X=1) \\ 
> P(Y) & P(Y=0) & P(Y=1) & 1 \\ 
> \end{array}$$
> $$
> \begin{array}{cccc}
> & Y=0 & Y=1 & P(X) \\ 
> X=0 & 0.1 & 0.2 & 0.3 \\ 
> X=1 & 0.3 & 0.4 & 0.7 \\ 
> P(Y) & 0.4 & 0.6 & 1 \\ 
> \end{array}
> $$
> 
> The initial joint probability distribution for random variables $X$ and $Y$ can be expressed as:
> 
> $$\begin{align*}
> P(X=1, Y=1) &= 0.1, \quad P(X=1, Y=2) = 0.2, \\
> P(X=2, Y=1) &= 0.3, \quad P(X=2, Y=2) = 0.4
> \end{align*}
> $$
> The marginal probability $P(X=x)$ for $x\in\{1,2\}$ can be calculated by summing the joint probabilities across all values of $Y$:
> $$\begin{align*} P(X=1) &= P(X=1, Y=1) + P(X=1, Y=2) = 0.1 + 0.2 = 0.3, \\ P(X=2) &= P(X=2, Y=1) + P(X=2, Y=2) = 0.3 + 0.4 = 0.7. \end{align*}$$
> Similarly, the marginal probability $P(Y=y)$ for $y\in\{1,2\}$ can be calculated by summing the joint probabilities across all values of $X$:
> $$\begin{align*}
> P(Y=1) &= P(X=1, Y=1) + P(X=2, Y=1) = 0.1 + 0.3 = 0.4, \\
> P(Y=2) &= P(X=1, Y=2) + P(X=2, Y=2) = 0.2 + 0.4 = 0.6.
> \end{align*}$$
> 
> So the marginal probabilities are$P(X=1) = 0.3$, $P(X=2) = 0.7$, $P(Y=1) = 0.4$, and $P(Y=2) = 0.6$.


## Conditional Probabilities:
The conditional probability can be put into words in the following fraction:
$$\frac{p(\text{What do we want to know?})}{p(\text{What we know.})}$$
In mathematical notation this results in the following term:
$$P(A|B) = \frac{P(A \cap B)}{P(B)}$$
where $P(A|B)$ denotes the probability of event A given event B, $P(A \cap B)$ is the probability of both A and B occurring, and $P(B)$ is the probability of event B occurring. $P(A \cap B)$ can be shortened to $P(A, B)$ and for conditioning to be possible, $P(B)$ needs to be defined. 

## Conditional Independence
$$P(A \cap B | C) = P(A | C) \cdot P(B | C)$$

where $P(A \cap B | C)$ denotes the probability of both event A and event B occurring given event C, and $P(A | C)$ and $P(B | C)$ are the conditional probabilities of events A and B, respectively, given event C.

Conditional independence describes the relationship between two events A and B, given a third event C. Two events A and B are conditionally independent given event C if the occurrence of one event (A) does not affect the probability of the other event (B) given the occurrence of the third event (C). In other words, if A and B are conditionally independent given C, then the probability of A and B occurring together given C is equal to the product of the probability of A occurring given C and the probability of B occurring given C.

Conditional independence is an important concept in many areas of statistics, including Bayesian inference and machine learning. It allows us to simplify complex models and make more accurate predictions by identifying and exploiting relationships between different events or variables.

> [!Example]-
> Let A represent the event of smoking, B represent the event of lung cancer, and C represent the event of age. Suppose we know that smoking (event A) increases the probability of lung cancer (event B), but this relationship is also strongly influenced by age (event C).
> If we condition on age (event C), we can say that smoking (event A) and lung cancer (event B) are conditionally independent given age (event C). In other words, the probability of smoking causing lung cancer given a person's age is the same as the probability of smoking causing lung cancer in the general population.
> Mathematically, we can express this as:
> $$P(A \cap B | C) = P(A | C) \cdot P(B | C)$$
> where $P(A \cap B | C)$ denotes the probability of both smoking and lung cancer occurring given age, and $P(A | C)$ and $P(B | C)$ are the conditional probabilities of smoking and lung cancer, respectively, given age.

## Joint Probabilities:
Joint probabilities are probabilities of two or more events occurring together. More Formally: <mark style="background: #FFB8EBA6;">the probability of a conjunction of N propositions (events),is usually called the joint probability </mark>that is, $P\left(A_1, A_2, \ldots, A_N\right.$ | $B)$. If we generalise the product rule to $N$ propositions we obtain what is known as the chain rule:
$$
\begin{gathered}
P\left(A_1, A_2, \ldots, A_N \mid B_{bg}\right)=P\left(A_1 \mid A_2, A_3, \ldots, A_N, B_{bg}\right) P\left(A_2 \mid A_3, A_4, \ldots, A_N, B_{bg}\right) \\
\cdots P\left(A_N \mid B_{bg}\right)
\end{gathered}
$$
$B_{bg}$ is the background information that is always present, because we do not assume that there are absolute probabilities (see [[Probability Theory Definitions]]). They are denoted as $P(A, B)$, where $A$ and $B$ are the events of interest and $B_{bg}$ is the background. Joint probabilities can be calculated using the formula:
$$P(A, B | B_{bg}) = P(A|B,B_{bg}) \cdot P(B|B_{bg})$$

Example:
Consider a deck of playing cards. Let A be the event of drawing a spade, and B be the event of drawing a queen. The probability of drawing a spade and a queen from the deck is:
$$P(A, B|B_{bg}) = P(A|B|B_{bg}) \cdot P(B|B_{bg}) = \frac{1}{13} \cdot \frac{4}{52} = \frac{1}{52}$$

These are the fundamental concepts of marginal probabilities, conditional probabilities, and joint probabilities. Understanding them can help analyze and solve various problems in probability theory and statistics.

