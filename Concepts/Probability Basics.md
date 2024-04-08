---
title: Probability Basics
date: 19-05-2023
time: 16:19
author: Luca Trautmann
tags: ['Mathematics','ML']
series: "Probability Theory"
chapter: 1
---
# Probability Basics
Probability theory is an extension of logic. The following summarises the most fundamental concepts.

## An Event
An event can be any occurence or statement like the following:
- _"Tomorrow it will rain."_
- _'The model parameter is between 1 and 2.'_
- _'The label for this image is 1'_

## Probability of an Event
The probability of an event is defined as follows:
$$P(\text{Label = 1}) = 0.87$$
This would then mean that the probability of the label being 1 is 0.87.


## Probabilities of Multiple Event 
### Conjunction
If we have two events $A$ and $B$ the __joint probability__ is defined as:
$$P(A \cap B) = P(A) \cdot P(B) \quad \text{if independent}$$
and:
$$P(A \cap B) = P(A) \cdot P(B|A) = P(B) \cdot P(A|B)\quad \text{if dependent}$$
where $P(A \cap B)$ denotes the probability of both event A and event B occurring, and $P(A)$ and $P(B)$ are the individual probabilities of events A and B, respectively. $P(B|A)$ is the conditional probability of B 'given' A.
### Union
$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

where $P(A \cup B)$ denotes the probability of event A or event B occurring (or both), $P(A)$ and $P(B)$ are the individual probabilities of events A and B, respectively, and $P(A \cap B)$ is the probability of both A and B occurring.

Note that if events A and B are mutually exclusive (i.e., cannot occur at the same time), then $P(A \cap B) = 0$, and the formula simplifies to:

$$P(A \cup B) = P(A) + P(B)$$

Related: [[Random Variables]], [[Bayes Theorem]] 

