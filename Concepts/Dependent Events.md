---
title: Dependent Events
date:
  - 12-02-2024
time: 15:37
author: Luca Trautmann
tags: 
series: PT
chapter: 3
status: Incomplete
modified: 2024-02-14
---
# Dependent Events
## Conditional Probabilities
In observing the outcomes of a random experiment, one is often interested in how the outcome of one event A is influenced by that of another event B. To characterise the relation between A and B, we introduce the conditional probability of A on the hypothesis B, i.e., the "probability of A occurring under the condition that B is known to have occurred."

$$
\mathbf{P}(A \mid B)=\frac{\mathbf{P}(A B)}{\mathbf{P}(B)}
\tag{3.3}$$

with the assumption that: $\mathbf{P}(B) > 0$

__In fact, the denominator in (3.3) is the total number of such outcomes, while the numerator is the total number of such outcomes leading to the occurrence of A.__

Intuition (from stackoverflow):

> By conditioning on B (the event that _has_ occured), you restrict your space of outcomes from $\Omega$ (the whole plane) to B only. You forget everything that is outside B. The probability of event A has to be measured with respect B, since the probability is between 0 and 1.

Therefore conditional probabilities are like zooming in. 

The following conditions apply;
1) $0 \leqslant \mathbf{P}(A \mid B) \leqslant 1$;
2) If $A$ and $B$ are incompatible, so that $A B=\varnothing$, then $\mathbf{P}(A \mid B)=0$;
3) If $B$ implies $A$, so that $B \subset A$, then $\mathbf{P}(A \mid B)=1$;
4) If $A_1, A_2, \ldots$ are mutually exclusive events with union $A=\bigcup_k A_k$, then
$$
\mathbf{P}(A \mid B)=: \sum_k \mathbf{P}\left(A_k \mid B\right)
$$
([[Combinations of Events#The Addition Law for Probabilities]]).