---
title: Group Delay
date: 06-07-2023
time: 13:18
author: Luca Trautmann
tags: []
series: "Audio-processing"
chapter: 1
---

# Group Delay
Group delay is a concept used in signal processing to describe the delay experienced by different frequency components of a signal as they pass through a system. In the context of the phase component of a short-time Fourier transform (STFT), group delay refers to the variation in the phase response of the STFT across different frequency bins.

The STFT represents a signal in the time-frequency domain by dividing it into small overlapping segments and calculating the Fourier transform of each segment. The resulting complex-valued spectrogram contains both magnitude and phase information.

The phase component of the STFT represents the phase shift applied to each frequency component of the signal during the analysis window. <mark style="background: #BBFABBA6;">Group delay specifically refers to the instantaneous rate of change of phase with respect to frequency, which can vary across different frequency bins.</mark>

In other words, group delay describes the time delay experienced by each frequency component of the signal as it passes through the system represented by the STFT. It characterizes the dispersion or distortion of different frequency components due to the system's frequency response.

Understanding the group delay can be important in various applications, such as audio processing, where it can affect the perceived timing and phase relationships between different frequency components of a signal.










# Chapters
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```