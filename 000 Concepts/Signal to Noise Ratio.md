---
title: Signal to Noise Ratio
date: 24-08-2023
time: 21:25
author: Luca Trautmann
tags: ['Thesis']
series: "Audio-processing"
chapter: 2
---

> [!Chapters]-
> ```dataview
> TABLE chapter as Chapter
> FROM "concepts"
> WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
> SORT chapter asc
> ```

# Signal to Noise Ratio
### Signal and Noise: A Summary

1. **Definitions**:
   - **Signal**: The actual information or data you want to observe, measure, or transmit.
   - **Noise**: Unwanted disturbances or fluctuations that interfere with the true signal. It can originate from various sources like electronic devices, environmental factors, or even from within the system itself.

2. **Signal-to-Noise Ratio (SNR)**: 
   - SNR measures the proportion of the desired signal's power to the power of the noise. A higher SNR indicates a clearer signal with less noise interference.
   - Expressed in decibels (dB) as: 
     $$\text{SNR}_{dB} = 10 \times \log_{10}\left(\frac{\text{Signal Power}}{\text{Noise Power}}\right)$$
   - A positive and high SNR implies a strong signal presence relative to noise. Conversely, a negative or low SNR suggests that noise levels are high compared to the signal.

3. **Impact on Information Transmission and Processing**:
   - High noise levels can degrade the quality of transmitted information, potentially causing errors in data transmission.
   - In imaging (like medical imaging or photography), noise can reduce the clarity and quality of the produced images.
   - In audio processing, noise manifests as background hiss or static, diminishing the clarity of the sound.

4. **Noise Reduction and Enhancement**:
   - Various techniques aim to enhance the SNR by reducing noise or amplifying the signal. Examples include filtering, averaging, and using error-correcting codes in communication systems.
   - Adaptive algorithms can be employed to minimize the impact of noise dynamically.

5. **Sources of Noise**:
   - **Thermal Noise**: Caused by random motion of electrons in conductors, inherent in all electronic devices.
   - **Quantization Noise**: Occurs in digital systems when continuous signals are converted to discrete values.
   - **Environmental Noise**: External disturbances, e.g., electromagnetic interference from other devices or cosmic sources.
   - **Internal System Noise**: Noise introduced by components or processes within the system.

6. **Random vs. Deterministic Noise**:
   - **Random Noise**: Unpredictable and varies over time (e.g., thermal noise). Its properties can often be statistically described (mean, variance).
   - **Deterministic Noise**: Follows a predictable pattern and can sometimes be compensated for or eliminated.

7. **Importance in System Design**:
   - Understanding the nature of noise and its impact on system performance is crucial for designing robust systems.
   - Many modern systems are designed to function even under considerable noise, demonstrating the importance of noise analysis and mitigation in real-world applications.

In conclusion, the relationship between signal and noise is pivotal in determining the performance and reliability of many systems. A strong grasp of this relationship is essential for effective system design, signal processing, and information transmission.









