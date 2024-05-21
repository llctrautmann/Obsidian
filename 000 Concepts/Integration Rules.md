---
title: Integration Rules
date: 12-06-2023
time: 16:52
author: Luca Trautmann
tags: ["Mathematics"]
series: "Mathematics & Statistics"
chapter: 5
---

# Integration Rules
1. Linearity of integration: $\int (a f(x) + b g(x)) \, dx = a \int f(x) \, dx + b \int g(x) \, dx$, where $a$ and $b$ are constants.

2. Adding integrals: $\int f(x) \, dx + \int g(x) \, dx = \int (f(x) + g(x)) \, dx$.

3. Subtracting integrals: $\int f(x) \, dx - \int g(x) \, dx = \int (f(x) - g(x)) \, dx$.

These rules allow you to break down complex integrals into simpler ones and combine them to solve more complicated integration problems.

1. Power rule: $\int x^n \, dx = \frac{1}{n+1} x^{n+1} + C$, where $C$ is the constant of integration.

2. Integration by parts: $\int u \, dv = uv - \int v \, du$, where $u$ and $v$ are functions of $x$.

3. Substitution rule: $\int f(g(x)) g'(x) \, dx = \int f(u) \, du$, where $u = g(x)$ and $du = g'(x) \, dx$.

4. Trigonometric integrals: $\int \sin(x) \, dx = -\cos(x) + C$, $\int \cos(x) \, dx = \sin(x) + C$, $\int \tan(x) \, dx = -\ln|\cos(x)| + C$.

5. Exponential and logarithmic integrals: $\int e^x \, dx = e^x + C$, $\int \ln(x) \, dx = x\ln(x) - x + C$.

6. Partial fraction decomposition: Involves breaking a rational function into simpler fractions that can be integrated separately.

7. Improper integrals: Integrals that have infinite limits of integration or are undefined at certain points.

These rules are fundamental to solving a wide range of integration problems.










# Chapters
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```