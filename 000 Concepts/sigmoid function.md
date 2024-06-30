---
title: sigmoid function
date:
  - 19-06-2024
time: 21:02
author: Luca Trautmann
tags:
  - ProbTheory
series: Probability Theory
🍙: いや
type: 
formula: 
aliases: 
modified: 2024-06-30
---
# sigmoid function


$$\large\tag{1}\sigma(a) \triangleq \frac{1}{1+e^{-a}}$$

## Noteworthy
- some useful things to keep in mind are:
$$\large\tag{2}
\begin{aligned}
\sigma(x) & \triangleq \frac{1}{1+e^{-x}}=\frac{e^x}{1+e^x} \\
\frac{d}{d x} \sigma(x) & =\sigma(x)(1-\sigma(x)) \\
1-\sigma(x) & =\sigma(-x) \\
\sigma^{-1}(p) & =\log \left(\frac{p}{1-p}\right) \triangleq \operatorname{logit}(p) \\
\sigma_{+}(x) & \triangleq \log \left(1+e^x\right) \triangleq \operatorname{softplus}(x) \\
\frac{d}{d x} \sigma_{+}(x) & =\sigma(x)
\end{aligned}
$$
