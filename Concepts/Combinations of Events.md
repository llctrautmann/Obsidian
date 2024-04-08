---
title: Combinations of Events
date: 09-02-2024
time: 20:11
author: Luca Trautmann
tags: 
series: PT
chapter: 2
modified: 2024-02-12
---
# Combinations of Events
## Elementary Events: The sample Space
The mutually exclusive outcomes of a random experiment are called _elementary events_ or _sample points_ denoted $$\omega$$
The set of all elementary events is the sample space:
$$
\Omega
$$
An event $A$ is said to be "associated with the elementary events of Q" if, given any $\omega$ in $\Omega$, we can always decide whether or not o leads to the occurrence of A. `//FIXME: Requires more explanations, I dont understand this completely`

$A$ denote both the event $A$ and the set of elementary events leading to the occurrence of $A$. Events are nothing more or less than subsets of some underlying sample space $\Omega$.

The certain event is equal to $\Omega$ and an impossible event is equal to the empty set $\emptyset$. 

Given two events $A_1$ and $A_2$, suppose $A_1$ occurs if and only if $A_2$ occurs. Then $A_1$ and $A_2$ are said to be identical (or equivalent), and we write $A_1=A_2$.

## Examples
### Example 1: 
In throwing a pair of dice, let $A_1$ be the event that "the total number of spots is even" and $A_2$ the event that "both dice turn up even or both dice turn up odd". Then $A_1=A_2$. (There is another explanation of this in [[Sets in Mathematics]]). 
`\\ This makes sense and I have checked it manually on paper` $\square$ 
### Example 2: 
In throwing three dice, let $A_1$ again be the event that "the total number of spots is even" and $A_2$ the event that "all three dice have either an even number of spots or an odd number of spots." Then $A_1 \neq A_2$.
`\\ In this case I have numbers that do not occur in one set but that do occur in the other set. For example 3,5 2 = 8, but 3 is odd and 2 is even. ` $\square$ 

## Mutually exclusive, Union, Intersection, Complement
### Mutually exclusive
$A_1$ and $A_2$ are mutually exclusive if the occurrence of one event precludes the occurrence of the other event. 

### Union
The union is the logical OR and hence describes events that are true if at least one subcomponent is true.
$$
A_1 \cup A_2
$$
or more general: 
$$
\mathop{\bigcup}_{k} A_{k}
$$

### Intersection
The intersection is the logical AND and is only true if all subcomponents are true.
$$
A_{1} \bigcap A_{2}
$$
or more general:
$$\mathop{\bigcap}_{k} A_{k}$$
### Complement
The complement is the opposite of $A$. It is hence: 
$$
\Omega - A = \bar{A}
$$
It also means: That $A$ does not occur. 

### Example 3:
Example 3. In throwing a pair of dice, let $A$ be the event that "the total number of spots is even," $A_1$ the event that "both dice turn up even," and $A_2$ the event that "both dice turn up odd." Then $A_1$ and $A_2$ are mutually exclusive, and clearly
$$
A=A_1 \cup A_2, \quad A_1=A-A_2, \quad A_2=A-A_1 .
$$
`\\ This makes intuitive sense and can be checked manually. `

> Thus the symbols for union, intersection, complement, etc. have their customary set-theoretic meaning. (Rozanov, 1977, p. 15)

![[Ven_Diagrams.png]]

### Additional Rules
From the rules above we can also conclude: 
1. If A is a subset of B, then B is not a subset of A
2. If A is B OR C, then not A is not B and not C
3. if A is A AND B then not A is not B and not C

1) If $A_1 \subset A_2$, then $\overline{A_1} \supset \overline{A_2}$;
2) If $A=A_1 \cup A_2$, then $\bar{A}=\overline{A_1} \cap \overline{A_2}$;
3) If $A=A_1 \cap A_2$, then $\bar{A}=\overline{A_1} \cup \bar{A}_2$.


## The Addition Law for Probabilities
For mutually exclusive events the probability of their union is the sum of each probability:
$$
\operatorname{P}(A)= \operatorname{P}(A_{1}) + \operatorname{P}(A_2)
$$
This can be extended: 
$$
\mathbf{P}\left(A_1 \cup A_2 \cup A_3\right)=\mathbf{P}\left(A_1 \cup A_2\right)+\mathbf{P}\left(A_3\right)=\mathbf{P}\left(A_1\right)+\mathbf{P}\left(A_2\right)+\mathbf{P}\left(A_3\right)
$$
an generalised into:
$$
\mathbf{P}\left(\bigcup_{k=1}^n A_k\right)=\sum_{k=1}^n \mathbf{P}\left(A_k\right)
$$
## Key relations involving Probabilities
### Mutually exclusive (easy)
For any events $A$, $A_1$, $A_2$ the following formulae hold:
$$
0 \leqslant \mathbf{P}(A) \leqslant 1
\tag{2.3}$$

$$
\mathbf{P}\left(A_1-A_2\right)=\mathbf{P}\left(A_1\right)-\mathbf{P}\left(A_1 \cap A_2\right)
\tag{2.4}$$
`//This can be easily explained with a Ven-diagram see [[Eq2.4VDG.png]]
$$
\mathbf{P}\left(A_1 \cup A_2\right)=\mathbf{P}\left(A_1\right)+\mathbf{P}\left(A_2\right)-\mathbf{P}\left(A_1 \cap A_2\right)
$$
`//Think about it, this makes also perfect sense. If not mutually exclusive, we would double count the piece in the middle. 
$$
\mathbf{P}\left(A_1\right) \leqslant \mathbf{P}\left(A_2\right) \quad \text { if } \quad A_1 \subset A_2
$$

### Not mutually exclusive (hard)
For events not mutually exclusive the following holds:
$$
\mathbf{P}\left(\bigcup_{k=1}^n A_k\right)=P_1-P_2+P_3-P_4+\cdots \pm P_n
$$
`// The proof is very complicated and not what I need to understand in depth`

THEOREM 2.3. If $A_1, A_2, \ldots$ is an "increasing sequence" of events, i.e., a sequence such that $A_1 \subset A_2 \subset \cdot$, then
$$
\mathbf{P}\left(\bigcup_k A_k\right)==\lim _{n \rightarrow \infty} \mathbf{P}\left(A_n\right) .
$$Similarly, we have
ThEOREm 2.3'. If $A_1, A_2, \ldots$ is a "decreasing sequence" of events, i.e., a sequence such that $A_1 \supset A_2 \supset \cdots$, then
$$
\mathbf{P}\left(\bigcap_k A_k\right)=\lim _{n \rightarrow \infty} \mathbf{P}\left(A_n\right)
$$
