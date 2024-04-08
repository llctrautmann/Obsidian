---
title: Notes on Probability Theory
date: 07-12-2023
time: 15:54
author: Luca Trautmann
tags:
  - Statistics
series: Probability Theory
chapter: 0
link: https://betanalpha.github.io/assets/case_studies/probability_theory.html
---

> [!Chapters]-
> ```dataview
> TABLE chapter as Chapter
> FROM "concepts"
> WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
> SORT chapter asc
> ```

# Notes on Probability Theory
# Setting a Foundation
A _set_ is a collection of elements and a _space_ is the collection of all elements under consideration. For example, A={1}, B={1,5,10,12}, and C={30,2,7}, are all sets contained in the space of _natural numbers_, $\mathbb{N}$={0,1,…}.

A is contained in B and hence A is a subset of B denoted:

$$A \subset B$$

A point set is a set containing only one element. The entire set is always a valid set as is the empty set $\emptyset$.

Sets are often defined implicitly via an inclusion criterion. These sets are denoted with the _set builder_ notation:

$$
A=\{x \in x \mid f(x)=0\},
$$
This reads as: <mark style="background: #FFB8EBA6;">the set of elements x in the space X such that the condition f(x)=0 holds</mark> 

>[!Example]
> $$
> E=\{\xi \in \Omega \mid X(\xi)=a\}
> $$
> Reads as: The elements in the set Omega, for which the application of the random variable X yields a holds. 


Throughout this case study we will use four sets to demonstrate the operations of set theory and probability theory. Our first two sets are finite intervals within the natural numbers,

$$
\begin{aligned}
& A_1=\{x \in \mathbb{N} \mid 4 \leq x \leq 7\} \\
& A_2=\{x \in \mathbb{N} \mid 7 \leq x \leq 9\}
\end{aligned}
$$

The latter two sets are finite intervals within the real numbers,

$$
\begin{aligned}
& B_1=\{x \in \mathbb{R} \mid-2 \leq x \leq 1\} \\
& B_2=\{x \in \mathbb{R} \mid 0 \leq x \leq 3\}
\end{aligned}
$$
# Set Operations
![[sets.png]]
## Set Complement
The set complement is a unary operation that maps one set into another set. Given a set, $A$, its complement, $A^C$, is defined by all of the elements _not_ in that set,
$$
\mathrm{A}^{\mathrm{C}}=\{\mathrm{x} \in \mathrm{X} \mid \mathrm{x} \notin \mathrm{A}\}
$$
For example, the complement of $\mathbf{A}_1$ contains all of the positive integers below 4 and above 7,
$$
A_1^c=\{x \in \mathbb{N} \mid x<4 \text { OR } x>7\}
$$

Similarly, the complement of $\mathrm{B}_1$ is given by
$$
B_1^c=\{x \in \mathbb{R} \mid x<-2 \text { OR } x>1\}
$$

By definition the complement of the empty set is the entire space, $\mathscr{\ell}^{\mathrm{C}}=\mathrm{X}$, and vice versa, $\mathrm{X}^{\mathrm{C}}=\varnothing$.

## Set Union
The set union is a binary operator that maps two sets into a third set. We can construct the union as the set of elements included in _either_ set,
$$
\mathrm{A}_1 \cup \mathrm{A}_2=\left\{\mathrm{x} \in \mathrm{x} \mid \mathrm{x} \in \mathrm{A}_1 \text { OR } \mathrm{x} \in \mathrm{A}_2\right\} \text {. }
$$
The union of any set and the empty set is just that set, $A \cup \emptyset=A$.

## Set Intersection
The set intersection is another binary operator that maps two sets into a third set. The intersection of two sets, is defined as the set of elements included in _both_ sets,

$$
\mathrm{A}_1 \cap \mathrm{A}_2=\left\{\mathrm{x} \in \mathrm{x} \mid \mathrm{x} \in \mathrm{A}_1 \text { AND } \mathrm{x} \in \mathrm{A}_2\right\}
$$

The intersection of any set and the empty set is just the empty set, $A \cup \emptyset=\emptyset$.

# Sigma Algebras
The collection of all sets in a space, X, is called the <mark style="background: #FFB8EBA6;">power set</mark>. If the space X is well-behaved, the number of sets can still contain pathological sets. Hence we usually do not consider the entire power set but only a restricted version of the set. For the restrictions to be valid it needs to follow some guiding principles.

For example, if a set $\mathbf{A}$ is in our restriction then We want its complement $A^C$ to also be in our restriction. If $A_1$ and $A_2$ are in our restriction then we also want the restriction to contain the union, $A_1 \cup A_2$, and the intersection, $A_1 \cup A_2$. In fact we often will need our restrictions to be closed under a countably infinite, or countable, number of unions or intersections. More precisely, given a countable collection of sets, $\left\{\mathrm{A}_1, \mathrm{~A}_2, \ldots\right\}$ we want both the countable union.
$$
\mathrm{U}_{\mathrm{n}=1}^{\infty} \mathrm{A}_{\mathrm{n}}
$$
and the countable intersection,
$$
\bigcap_{n=1}^{\infty} A_n
$$
A restricted collection of sets satisfying these closure properties is called a $\sigma$-algebra over the space X and a choice of $\sigma$-algebra over $\mathrm{X}$ will be denoted with a calligraphic font $\mathcal{F}$.

<mark style="background: #FFB8EBA6;">An important benefit of these closure properties is that they ensure that any non-constructible sets that may be lurking within the power set don’t persist into a σ-algebra. Consequently identifying any σ-algebra removes many of the pathological behaviors that arise in uncountably-large spaces.</mark>

Most spaces that are being used in ML and other applications (e.g. integers, natural numbers, real numbers) always form a natural $\sigma$-algebra. So we don't need to worry about them. That said, because avoiding the pathologies of non-constructible sets is critical to a mathematically well-defined probability theory, $\sigma$-algebras will be a common occurrence.

# Topology
A topology on a space, X, is a collection of sets that contains the empty set and the full space and is closed under countable unions and finite intersections. The sets in a given topology are called topologically open sets and the complement of any open set is called a topologically closed set. 

The topology of a space provides a formal way to define important properties like continuity. For example, the fundamental differences between discrete and continuous spaces arise from their different topologies. In particular, all of the common spaces, such as the integers and the real numbers, have unique topologies from which many of their more-intuitive properties arise.

# Functions
A function is a relation that associates elements in one space to elements in another space. If a function, $f$, maps elements in the space $X$ to elements in the space $Y$ then we write
$$
\mathbf{f}: \mathbf{X} \rightarrow \mathbf{Y}
$$

If we want to be particularly explicit and denote how a particular element $\mathrm{X} \in \mathrm{X}$ maps into elements of $\mathrm{Y}$ then we can also write
$$
\begin{aligned}
\mathbf{f}: X & \rightarrow Y \\
\mathbf{x} & \mapsto \mathbf{f}(\mathbf{x})
\end{aligned}
$$
A function also induces a mapping from sets in the input space, X, to sets in the output space, Y, by applying the function to each individual element in the input set,
$$
f_*(A)=\left\{y \in Y \mid f^{-1}(y) \in A\right\}
$$
This induced map is called a <mark style="background: #FFB8EBA6;">pushforward map over sets</mark>

In contrast a pullback set maps from the output space Y to the input space X through an inverse function. 
$$
f^*(B)=\{x \in X \mid f(x) \in B\}
$$

# Mathematical Logistics
Probability theory is simply the study of an object, a probability distribution that assigns values to sets, and the transformations of that object.

## Probability Distributions
From an abstract mathematical perspective, probability is surprisingly boring. <mark style="background: #FFB8EBA6;">Probability is simply a positive, conserved quantity that we want to _distribute_ across a given space – in particular it does not necessarily refer to anything inherently random or uncertain. If we rescale this distribution in terms of the relative proportions of the total amount then regardless of the nature of this conserved quantity we can treat it as unit-less with total amounting to 1.</mark>

A probability distribution defines a mathematically self-consistent allocation of this conserved quantity across $X$. If $A$ is a subset of $\mathbf{X}$ then we write $\mathbb{P}_\pi[\mathbf{A}]$ as the probability assigned to $\mathbf{A}$ by the probability distribution $\pi$.

$$\mathbb{P}_\pi[\mathbf{A}]$$
Any distribution of probability needs to be exhaustive (the probability of everything needs to be 1). And it needs to be consistent in the sense that any partition of the space X needs to combine into the total. 
![[partition1.png]]
![[partition2.png]]
Or as a simple equation:
$$
\mathbb{P}_\pi\left[A_1\right]+\mathbb{P}_\pi\left[A_2\right]=\mathbb{P}_\pi[X]=1
$$

More formally we want the allocation of probability to any collection of disjoint sets, $A_n \cap A_m=0, n \neq m$ to be the same as the allocation to the union of those sets,
$$
\sum_{n=1}^N \mathbb{P}_\pi\left[A_n\right]=\mathbb{P}_\pi\left[U_{n=1}^N A_n\right],
$$
Which just means that the total is the sum of its parts and parts are composed of subparts. 

Consistency over any finite collection of sets is known as <mark style="background: #FFB8EBA6;">finite additivity</mark> and this would be sufficient if there were only a finite number of subsets in X.
> [!EX]-


Consequently in general we need our probability distributions to be countably additive across any disjoint sets, $\mathrm{A}_{\mathrm{n}} \cap \mathrm{A}_{\mathrm{m}}=0, \mathrm{n} \neq \mathrm{m}$,
$$
\sum_{n=1}^{\infty} \mathbb{P}_\pi\left[A_n\right]=\mathbb{P}_\pi\left[\cup_{n=1}^{\infty} A_n\right]
$$

This all sounds well and good, but it turns out that we cannot construct probability distributions that satisfy any kind of additivity for all subsets of every space. The problem are non-constructible sets. It turns out that when a space features non-constructible subsets we can combine a finite number of them, $\left\{\mathfrak{A}_1, \ldots, \mathfrak{A}_N\right\}$, in certain way to achieve <mark style="background: #FFB8EBA6;">subadditivity</mark>,
$$
\sum_{n=1}^N \mathbb{P}_\pi\left[\mathfrak{A}_n\right]>\mathbb{P}_\pi\left[\cup_{n=1}^N \mathfrak{A}_n\right]
$$
even when $\mathfrak{A}_{\mathrm{n}} \cap \mathfrak{A}_{\mathrm{m}}=0, \mathrm{n} \neq \mathrm{m}$. We can also combine a finite number of different non-constructible subsets to achieve <mark style="background: #FFB8EBA6;">superadditivity</mark>,
$$
\sum_{n=1}^N \mathbb{P}_\pi\left[\mathfrak{A}_n\right]<\mathbb{P}_\pi\left[\cup_{n=1}^N \mathfrak{A}_n\right] !
$$

In other words, there is no way that we can engineer a selfconsistent distribution of probability across non-constructible sets. Fortunately this pathological behavior isn't terminal because we already know how to avoid non-constructible sets in practice! All we have to do is limit our probability distributions to any well-defined $\sigma$ algebra, $\mathcal{F}$. Hence we need to limit out probability distribution to well-defined $\sigma$-algebras. 

## Kolmogorov Axioms / Axioms of Probability
- A probability distribution $\pi$ on a space $\mathbf{X}$ with $\sigma$-algebra $\mathcal{F}$ is a mapping from $\mathcal{F}$ to the real numbers $[0,1]$,
$$
\begin{aligned}
\mathbb{P}_\pi: \mathcal{F} & \rightarrow[0,1] \\
\mathrm{A} & \mapsto \mathbb{P}_\pi[\mathrm{A}] .
\end{aligned}
$$
- This mapping defines a lossless allocation, $\mathbb{P}_\pi[\mathrm{X}]=1$.
- This mapping defines a consistent allocation for any collection of disjoint sets in $\square$,
$$
\begin{gathered}
\mathbb{P}_\pi\left[\cup_{n=1}^{\infty} A_n\right]=\sum_{n=1}^{\infty} \mathbb{P}_\pi\left[A_n\right], \\
A_n \cap A_m=0, n \neq m .
\end{gathered}
$$

The more familiar rules of probability theory can all be derived from these axioms. For example the consistency condition implies that
$$
\mathbb{P}_\pi[\mathrm{A}]+\mathbb{P}_\pi\left[\mathrm{A}^{\mathrm{c}}\right]=\mathbb{P}_\pi[\mathrm{X}]=1
$$
or
$$
\mathbb{P}_\pi[\mathrm{A}]=1-\mathbb{P}_\pi\left[\mathrm{A}^{\mathrm{c}}\right]
$$

With a little work one can also derive the probability sum rules,
$$
\mathbb{P}_\pi\left[\mathrm{A}_1 \cup \mathrm{A}_2\right]=\mathbb{P}_\pi\left[\mathrm{A}_1\right]+\mathbb{P}_\pi\left[\mathrm{A}_2\right]-\mathbb{P}_\pi\left[\mathrm{A}_1 \cap \mathrm{A}_2\right],
$$
and
$$
\mathbb{P}_\pi\left[\mathrm{A}_1 \cap \mathrm{A}_2\right]=\mathbb{P}_\pi\left[\mathrm{A}_1\right]+\mathbb{P}_\pi\left[\mathrm{A}_2\right]-\mathbb{P}_\pi\left[\mathrm{A}_1 \cup \mathrm{A}_2\right]
$$
__In summary:__ 
- A probability distribution defined by Kolmogorov's axioms is completely specified by the probability triplet $(\mathbf{X}, \mathcal{F}, \pi)$ which is often denoted more compactly as $$\mathrm{X} \sim \pi$$and reads itself as "X distributed by $\pi$". In such cases we always assume a valid $\sigma$-algebra underlying the entire thing. Condensed into symbols the entire derivation of then fundamentals of probability theory can be can be summarised with the following symbols:$$\left [\Omega, \mathcal{F}_{\sigma}, X^{-1}, X_{\mathbb{R}}, \mathbb{P}_{[0,1]} \right ]$$
- Another good reference can be found here [[@park2019]].

# Probability and Densities 
_Density representations_ exploit the particular structure of $X$ to fully characterise a probability distribution with special functions.