---
title: Signal Processing
date: 01-09-2023
time: 14:55
author: Luca Trautmann
tags: []
series: "Audio-processing"
chapter: 3
---

> [!Chapters]-
> ```dataview
> TABLE chapter as Chapter
> FROM "concepts"
> WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
> SORT chapter asc
> ```

# Basic Signal Representation 
- Speech signals are sound signals, defined as pressure variations travelling through the air.
- A speech signal is then represented by a sequence of numbers $x_n$, which represent the relative air pressure at time-instant $n \in \mathbb{N}$. This representation is known as pulse code modulation often abbreviated as PCM. The accuracy of this representation is then specified by two factors; 1 ) the sampling frequency (the step in time between $n$ and $n+1$ ) and 2) the accuracy and distribution of amplitudes of $x_n$.

## Sampling Rate
- The Nyquist frequency is half the sampling rate $F_s$ and defines the upper end of the largest bandwidth $\left[0, \frac{F_s}{2}\right]$












