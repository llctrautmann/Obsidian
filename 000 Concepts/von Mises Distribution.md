---
title: von Mises Distribution
date:
  - 23-08-2023
time: 21:11
author: Luca Trautmann
tags: 
series: Machine Learning Fundamentals
chapter: 12
modified: 2024-05-07
---

> [!Chapters]-
> ```dataview
> TABLE chapter as Chapter
> FROM "concepts"
> WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
> SORT chapter asc
> ```

# von Mises Distribution
Problem 5.3 Suppose we want to build a network that predicts the direction $y$ in radians of the prevailing wind based on local measurements of barometric pressure $\mathbf{x}$. A suitable distribution over circular domains is the von Mises distribution (figure 5.13 from book):
$$
\operatorname{Pr}(y \mid \mu, \kappa)=\frac{\exp [\kappa \cos [y-\mu]]}{2 \pi \cdot \operatorname{Bessel}_0[\kappa]},
$$
where $\mu$ is a measure of the mean direction and $\kappa$ is a measure of the concentration (i.e., the inverse of the variance). The term Bessel $_0[\kappa]$ is a modified Bessel function of order 0 .

Use the recipe from section 5.2 to develop a loss function for learning the parameter $\mu$ of a model $\mathrm{f}[\mathbf{x}, \phi]$ to predict the most likely wind direction. Your solution should treat the concentration $\kappa$ as constant. How would you perform inference?
Answer
$$
\begin{aligned}
L & =\sum_{i=1}^I-\log \left[\frac{\exp \left[\kappa \cos \left[y-\mathrm{f}\left[\mathbf{x}_i, \phi\right]\right]\right]}{2 \pi \cdot \operatorname{Bessel}_0[\kappa]}\right] \\
& =\sum_{i=1}^I-\kappa \cos \left[y-\mathrm{f}\left[\mathbf{x}_i, \phi\right]\right]+\log \left[\operatorname{Bessel}_0[\kappa]\right]\\
L&=\sum_{i=1}^I-\cos \left[y-\mathrm{f}\left[\mathbf{x}_i, \phi\right]\right],
\end{aligned}
$$
by removing constant additive and multiplicative factors.


Certainly, when describing this dataset and presenting it in a talk, you'd want to ensure your audience understands the dataset's design, its motivations, and its potential applications. Here's how I'd describe and present the dataset:

---

**Slide 1: Introduction**

**Title:** Exploring Cyclical Data with Custom Dataset

**Content:**
- Today, we will look at a custom dataset designed to explore the challenges and intricacies of working with cyclical data, particularly angle measurements.
- The dataset maps linear values to angle measurements bound between \([- \pi, \pi]\).

---

**Slide 2: Motivation**

**Title:** Why Study Cyclical Data?

**Content:**
- Cyclical data appears frequently in real-world applications:
  - Time of day (morning, afternoon, evening)
  - Seasonal data (spring, summer, fall, winter)
  - Angle measurements in fields like robotics or navigation.
- Traditional linear approaches may not capture the essence of cyclical patterns.
- Our dataset offers a comprehensive playground to test and develop methods tailored for cyclical data.

---

**Slide 3: Dataset Composition**

**Title:** Components of Our Custom Dataset

**Content (with visuals for each segment):**
1. **Linear Mapping:** Linear data points ranging from 0 to 10, mapped directly to angles between \([- \pi, \pi]\). This serves as a baseline representation.
2. **Boundary Data:** 4096 samples densely populated near the boundaries (between 9.8 and 10.2). This helps to understand and handle edge cases and wrapping effects.
3. **Shifted Data:** Data points extended beyond the normal range, capturing the cyclical nature of the dataset.
4. **Noisy Data:** Adds variability and simulates real-world noise, especially near boundaries, making our models more robust.
5. **Random Sampling:** Data points sampled randomly to encapsulate a wide range of possibilities.

---

**Slide 4: Challenges & Opportunities**

**Title:** What Can We Learn?

**Content:**
- **Wrapping Challenges:** How do models handle values that wrap around the boundary?
- **Noise Tolerance:** Can the model resist and generalize over noise, especially near tricky boundaries?
- **Shifted Interpretation:** How does shifting values affect predictions? Does the model truly understand cyclical nature?
- **Robustness:** Random sampling tests the model's ability to generalize across the entire range of values.

---

**Slide 5: Potential Applications**

**Title:** Real-world Use-cases

**Content:**
- **Robotics:** Angle measurement and prediction for robotic arms.
- **Navigation:** Predicting direction changes in navigation tasks.
- **Time-series Forecasting:** Predicting cyclical patterns like stock prices, energy usage, or seasonal trends.

---

**Slide 6: Conclusion**

**Title:** Embracing Cyclical Challenges

**Content:**
- Our custom dataset offers a rich platform to understand and develop solutions for cyclical data.
- By addressing the challenges posed by this dataset, we pave the way for better handling of real-world cyclical data challenges.
- Looking forward to seeing innovative models and solutions built on top of this dataset!

---

This approach lays out the motivation, design, and importance of the dataset, ensuring the audience understands its value and potential applications.


Yes, that's an accurate characterization. At its core, a neural network trained on this dataset would be approximating a function that maps real values to angles in the range \([- \pi, \pi]\).

In more detail:

When you train a neural network on this dataset, you are effectively teaching it to understand and capture the underlying relationship between your input data (the real values) and the output labels (the angles). Given that the main task involves predicting an angle based on a real value, the network acts as a function approximator for this specific transformation.

However, it's crucial to emphasize the nuances and complexities involved due to the cyclical nature of the data. The challenges of boundary cases, noise, shifted values, and random samples mean that this isn't just a straightforward function approximation task. The model needs to capture and understand the cyclical patterns inherent in the data, especially around the boundaries.

So, while the primary goal is function approximation, the context (dealing with cyclical data) adds layers of complexity that make the task richer and more challenging.

