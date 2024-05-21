---
title: Griffin-Lim Algorithm
date: 17-09-2023
time: 16:50
author: Luca Trautmann
tags:
  - Thesis
series: Signal Processing
chapter: 2
---

> [!Chapters]-
> ```dataview
> TABLE chapter as Chapter
> FROM "concepts"
> WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
> SORT chapter asc
> ```

# Griffin-Lim Algorithm
Imagine that you have a magnitude spectrogram, because, let’s say, your processing method did some alterations to the original one and you have only the output magnitude part, but you want to return to the time series from it.

Griffin-Lim allows you to converge towards the estimated phase layer by doing those simple steps:

1. Create a complex matrix, insert you magnitude spectrogram as a real layer, and create imaginary layer of uniform noise (Now you have amplitude information but still no phase).
2. Perform ISTFT on it (Now you have time series based on amplitude information only).
3. Calculate STFT of obtained time series (Now you extract a little bit of phase information from the time series, but it’s still highly imperfect because time series was imperfect).
4. In that STFT, which is a complex matrix, change real layer to your original magnitude spectrogram (Now you have complex spectrogram with unchanged amplitude information from your starting mag spec, but now you have a little bit of useful phase information).
5. Return to point 2.
6. Iterate until you are satisfied.

You can see that from iteration to iteration your phase layer will be more and more useful, and hence your time series obtained in point 2 will be better and better. This algorithm is convergent so the only thing you have to decide is number of iterations.

Keep in mind that due to resolution rounding in STFT, your output signal may have slightly different length than the original time series.










