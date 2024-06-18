---
title: Bayes Theorem
date:
  - 17-05-2023
time: 13:07
author: Luca Trautmann
tags:
  - ML
series: Probability Theory
chapter: 5
modified: 2024-06-18
formula: $P(H|D, B) = \frac{P(H|B)\times P(D|H,B)}{P(D|B)}$
---
# Terminology

>$$P(H|D, B) = \frac{P(H|B)\times P(D|H,B)}{P(D|B)}$$

- $P(H|D,B)$ is the posterior
- $P(H|B)$ is the prior
- $P(D|H,B)$ is the likelihood
- $P(D|B)$ is the evidence or marginal likelihood

## Conceptual Explanation
__Bayes Theorem is a fundamental theorem of Probability Theory that is used to update knowledge about the likelihood of beliefs occurring__. It is a mathematical formula that describes the probability of an event based on prior knowledge or conditions that may be related to the event. It is named after the Reverend Thomas Bayes, an 18th-century British statistician and theologian who first formulated the theorem.

The theorem is expressed mathematically as $P(H|D, B) = \frac{P(H|B)\times P(D|H,B)}{P(D|B)}$, where $P(H|D,B)$ is the probability of event H occurring given that event D has occurred, $P(D|H,B)$ is the probability of event D occurring given that event H has occurred, $P(H|B)$ is the prior probability of event H occurring, and $P(D|B)$ is the prior probability of event D occurring.

In essence, Bayes Theorem allows us to update our prior beliefs or probabilities about an event in light of new evidence. It is widely used in statistics, machine learning, and decision theory to make predictions and draw conclusions based on available data.

## Prior
According to the logical interpretation there are no absolute probabilities, all are conditional on some background information. $P(H | B)$ conditioned only on the background B is called a prior probability.
## Likelihood

## Marginal Likelihood

## Posterior 
Once we incorporate some additional information $D$ we call it a posterior probability, $P(H | D, B)$. This is the updated belief statement. 

# Detailed Derivation for me
## What I needed to understand 
### Mathematically
- $P(H \land D) = P(D \land H)$ aka. the commutative property of intersection (logical AND)
- We also know from the product rule that: $P(H,D) = P(H) \times P(D|H)$ 
- Hence we know that: $P(H,D) = P(H) \times P(D|H) =  P(D,H) =  P(D) \times P(H|D)$
So this gives me the following _Zwischenschritt_:
$$P(H,D) = P(H) \times P(D|H) =  P(D) \times P(H|D)$$
Rules applied:
- product rule of probability
- commutative property of intersection

This now allows us to derive Bayes rule:

$$\begin{align*}
P(H,D) &= P(H) \times P(D|H) = P(D) \times P(H|D) \\\\
 P(D) \times P(H|D) &= P(H) \times P(D|H) \\\\
P(H|D) &= \frac{P(H)\times P(D|H)}{P(D)}\\\\
\end{align*}$$
### Conceptually
Discrete probability problems result in a concrete number for the outcome of the posterior probability. But continuous problems result in a new probability density function. 




### Law of Total Probability

   $$P(A) = \sum_i P(A \mid B_i) \cdot P(B_i)$$

1. Partition of the Sample Space: The sample space $\Omega$ is divided into a collection of mutually exclusive events $B_1, B_2, \ldots, B_n$, denoted as $B$. This means that each $B_i$ represents a distinct and non-overlapping outcome that covers the entire sample space. In other words, any outcome in $\Omega$ belongs to exactly one of the events $B_i$. Mathematically, we have $\Omega = B_1 \cup B_2 \cup \cdots \cup B_n$, and $B_i \cap B_j = \emptyset$ (the intersection of any two events $B_i$ and $B_j$ is an <mark style="background: #FFB8EBA6;">empty set</mark>).

2. Event $A$ as a Union of Intersections: The event $A$ is defined as the union of its intersections with each event $B_i$. In other words, $A$ can occur if any of the events $B_i$ occur, and the intersection between $A$ and each $B_i$ represents the outcomes that satisfy both $A$ and $B_i$. Symbolically, $A = (B_1 \cap A) \cup (B_2 \cap A) \cup \cdots \cup (B_n \cap A)$.

3. Using Axioms of Probability and Conditional Probability: The rule of total probability is derived by applying the axioms of probability and the definition of conditional probability. According to the definition of conditional probability, $P(A \mid B_i)$ represents the probability of event $A$ occurring given that event $B_i$ has occurred.

4. Deriving the Rule of Total Probability: The rule of total probability states that the probability of event $A$ can be calculated by summing the probabilities of $A$ conditioned on each of the events $B_i$, weighted by the probabilities of each $B_i$. Mathematically, this can be expressed as:

   $$P(A) = \sum_i P(A \mid B_i) \cdot P(B_i)$$

   Here, $P(B_i)$ represents the probability of event $B_i$ occurring, and $P(A \mid B_i)$ represents the conditional probability of $A$ given that $B_i$ has occurred. By summing these conditional probabilities weighted by the probabilities of the corresponding events $B_i$, we obtain the total probability of event $A$.

In summary, the rule of total probability provides a way to calculate the probability of an event $A$ by considering its intersections with a partition of the sample space, using conditional probabilities and the probabilities of the partition events. It is a useful tool for solving probability problems when the sample space can be divided into mutually exclusive events.

To derive the equation $P(A) = \sum_i P(A \mid B_i) \cdot P(B_i)$ from the expression $A = (B_1 \cap A) \cup (B_2 \cap A) \cup \cdots \cup (B_n \cap A)$, we can use the definition of probability and the properties of unions and intersections. Here's the step-by-step derivation:

1. Start with the expression: $A = (B_1 \cap A) \cup (B_2 \cap A) \cup \cdots \cup (B_n \cap A)$.

2. Take the probability of both sides of the equation: $P(A) = P\left((B_1 \cap A) \cup (B_2 \cap A) \cup \cdots \cup (B_n \cap A)\right)$.

3. Apply the probability of a union: $P(A) = P(B_1 \cap A) + P(B_2 \cap A) + \cdots + P(B_n \cap A)$.

4. Use the definition of conditional probability: $P(A) = P(A \mid B_1) \cdot P(B_1) + P(A \mid B_2) \cdot P(B_2) + \cdots + P(A \mid B_n) \cdot P(B_n)$.

5. Rearrange the terms: $P(A) = \sum_i P(A \mid B_i) \cdot P(B_i)$.

By breaking down the event $A$ into its intersections with each $B_i$ and applying the definition of conditional probability, we can express the probability of $A$ as a sum of the conditional probabilities $P(A \mid B_i)$ multiplied by the probabilities $P(B_i)$. This is known as the rule of total probability.