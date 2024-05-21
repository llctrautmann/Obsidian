---
title: Mel Spectrograms
date: 27-06-2023
time: 17:16
author: Luca Trautmann
tags: []
series: "Information Theory"
chapter: 3
---

# Mel Spectrograms
## Introduction
Mel spectrograms are a fundamental tool in the field of AI audio research. They provide a perceptually relevant representation of audio frequencies by considering how humans perceive sound. Unlike the linear representation of frequencies in traditional spectrograms, mel spectrograms utilise the Mel scale, a logarithmic scale that maps Hertz into "mels." The Mel scale is named after the word "melody," as it was initially developed to model the human perception of musical pitch. The scale is designed to mimic the non-linear relationship between the physical properties of sound waves and our perception of them. By using the Mel scale, mel spectrograms can capture the essential perceptual characteristics of audio signals more accurately.

## Mathematical Explanation
The Mel scale is defined by a mathematical formula that converts Hertz into mels. This conversion is based on a set of critical points, known as "mel filters," that divide the frequency range into distinct bands. Each mel filter is shaped like a triangular window, with its peak centered at a specific frequency. The width of the triangular window increases as the frequency increases, reflecting the fact that humans have a higher resolution for lower frequencies than for higher ones.

To compute a mel spectrogram, the audio signal is first divided into short overlapping frames. For each frame, the Fourier transform is applied to obtain the power spectrum, which represents the distribution of signal energy across different frequencies. Then, the power spectrum is passed through a bank of mel filters, and the energy within each filter is summed. This results in a set of values that represent the energy in different frequency bands, according to the Mel scale.

The final step in generating a mel spectrogram involves taking the logarithm of the filterbank energies, which helps compress the spectrogram's dynamic range. This logarithmic transformation is based on the observation that our perception of loudness is also logarithmic. The resulting mel spectrogram can be visualised as a 2D matrix, where the x-axis represents time and the y-axis represents the mel frequency bins.


 









# Chapters
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```