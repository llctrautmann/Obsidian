---
title: Complex Noise and SNR
date: 24-08-2023
time: 20:57
author: Luca Trautmann
tags: ['Thesis']
series:
chapter: 
---

> [!Chapters]-
> ```dataview
> TABLE chapter as Chapter
> FROM "concepts"
> WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
> SORT chapter asc
> ```

# Complex Noise and SNR

Absolutely, let's break down the procedure step-by-step and explain the underlying mathematics and necessary background concepts.

### 1. **Complex Numbers and Gaussian Noise**

#### Complex Numbers:
Complex numbers consist of two parts: a real part and an imaginary part. They can be represented in the form \(a + bj\), where \(a\) is the real part, \(b\) is the imaginary part, and \(j\) is the imaginary unit (in engineering, \(j\) is typically used instead of \(i\), which is more common in pure mathematics).

#### Gaussian Noise:
Gaussian noise is random signal noise derived from a Gaussian distribution. In the context of adding noise to a complex signal, both the real and imaginary parts of the noise are generated independently from Gaussian distributions.

```python
noise_real = torch.randn_like(stft.real)
noise_imag = torch.randn_like(stft.imag)
noise = torch.complex(noise_real, noise_imag)
```

In the code, `torch.randn_like` generates noise with a Gaussian distribution (mean = 0, standard deviation = 1) that has the same shape as the `stft.real` and `stft.imag`, respectively.

### 2. **Power of a Signal**

Power, in signal processing, refers to the mean squared magnitude of the signal. For complex signals, it's the sum of the squares of the real and imaginary components:

\[ \text{Power} = \frac{1}{N} \sum_{n=0}^{N-1} |x(n)|^2 \]

where \(N\) is the number of samples and \(x(n)\) is the complex signal value at index \(n\).

```python
signal_power = torch.mean(stft.abs().square())
noise_power = torch.mean(noise.abs().square())
```

In these lines, `stft.abs().square()` computes the squared magnitude of each element of the complex tensor `stft`. The `torch.mean` function then calculates the mean value over all elements, yielding the average power.

### 3. **Signal-to-Noise Ratio (SNR)**

SNR is a measure that compares the level of the desired signal to the level of background noise. It's defined as the ratio of the power of the signal to the power of the noise. When expressed in decibels (dB), it's given by:

\[ \text{SNR}_{dB} = 10 \times \log_{10}\left(\frac{\text{Signal Power}}{\text{Noise Power}}\right) \]

To achieve a specific SNR, you can adjust the noise level. If you have a signal and want to add noise to it such that the resulting noisy signal has a given SNR, you can scale the noise:

\[ K = \sqrt{\frac{\text{Signal Power}}{\text{Noise Power} \times 10^{\frac{\text{SNR}_{dB}}{10}}}} \]

```python
K = torch.sqrt(signal_power / (noise_power * 10**(desired_snr_dB / 10)))
```

Here, `K` is a scaling factor for the noise. This scaling ensures that when the noise is added to the original signal, the resulting SNR is close to the desired value.

### 4. **Addition of Scaled Noise to the Original Signal**

After scaling the noise, it's added to the original signal:

```python
noisy_sig = stft + K * noise
```

The resulting `noisy_sig` will have an approximate SNR of `desired_snr_dB`.

### **Background Concepts**:

- **Decibels (dB)**: Decibel is a logarithmic unit used to describe ratios. In signal processing, it's often used to express the ratio of two power quantities. When dealing with power, the relationship is \(X_{dB} = 10 \times \log_{10}(X)\). The logarithmic scale helps to manage and compare signals and noises of varying magnitudes in a more interpretable manner.

- **Fourier Transform & STFT**: While not explicitly detailed in the code, the variable name `stft` suggests the Short-Time Fourier Transform, a method to analyze the frequency content of signals. The STFT represents a signal in the time-frequency domain, giving insight into how different frequency components evolve over time.

Overall, this procedure allows one to simulate realistic, noisy environments when working with signals, which is essential for robustly testing signal processing algorithms or systems.









