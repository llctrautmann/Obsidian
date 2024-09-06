---
modified: 2024-09-06
---
I apologize for the oversight. You're right, MathJax is a better way to display mathematical expressions. Here's the explanation using MathJax notation:

When dealing with summation signs in differentiation, remember these key principles:

1. Linearity of differentiation:
   The derivative of a sum is the sum of the derivatives.

   $$\frac{d}{dx} \left[\sum f_i(x)\right] = \sum \left[\frac{d}{dx} f_i(x)\right]$$

2. Constant terms:
   If the summation index is not the variable of differentiation, treat it as a constant.

3. Variable limits:
   Be cautious with variable limits of summation; they may require additional consideration.

4. Common scenarios:

   a. Fixed limits:
   $$\frac{d}{dx} \left[\sum_{i=1}^n f_i(x)\right] = \sum_{i=1}^n \left[\frac{d}{dx} f_i(x)\right]$$

   b. Variable upper limit:
   $$\frac{d}{dx} \left[\sum_{i=1}^x f_i\right] = f_x + \sum_{i=1}^{x-1} \left[\frac{d}{dx} f_i\right]$$

   c. Variable lower limit:
   $$\frac{d}{dx} \left[\sum_{i=x}^n f_i\right] = -f_x + \sum_{i=x+1}^n \left[\frac{d}{dx} f_i\right]$$

5. Example:
   For $f(x) = \sum_{i=1}^n ix^2$
   $$f'(x) = \sum_{i=1}^n \left[\frac{d}{dx} (ix^2)\right] = \sum_{i=1}^n 2ix$$

Remember, the specific approach may vary depending on the complexity of the function inside the summation and the nature of the limits. Always consider the context of the problem when differentiating expressions involving summations.

Let's differentiate this expression with respect to μ. We'll do this step-by-step:

1) First, note that σ is constant with respect to μ, so we can treat -1/(2σ²) as a constant factor.

2) Using the linearity of differentiation, we can move the derivative inside the summation:

   $$\frac{d}{d\mu}\left[-\frac{1}{2\sigma^2}\sum_{n=1}^N(x_n-\mu)^2\right] = -\frac{1}{2\sigma^2}\sum_{n=1}^N\frac{d}{d\mu}(x_n-\mu)^2$$

3) Now, let's focus on differentiating (x_n - μ)². Using the chain rule:

   $$\frac{d}{d\mu}(x_n-\mu)^2 = 2(x_n-\mu)\frac{d}{d\mu}(x_n-\mu) = 2(x_n-\mu)(-1) = -2(x_n-\mu)$$

4) Substituting this back into our expression:

   $$-\frac{1}{2\sigma^2}\sum_{n=1}^N\frac{d}{d\mu}(x_n-\mu)^2 = -\frac{1}{2\sigma^2}\sum_{n=1}^N[-2(x_n-\mu)]$$

5) Simplifying:

   $$\frac{1}{\sigma^2}\sum_{n=1}^N(x_n-\mu)$$

Therefore, the derivative of the given expression with respect to μ is:

$$\frac{1}{\sigma^2}\sum_{n=1}^N(x_n-\mu)$$

This result is a key step in deriving the maximum likelihood estimate for the mean of a Gaussian distribution.

The linearity of differentiation is a fundamental property that states:

1. The derivative of a sum is the sum of the derivatives:

   $$\frac{d}{dx}[f(x) + g(x)] = \frac{d}{dx}f(x) + \frac{d}{dx}g(x)$$

2. The derivative of a constant multiple is the constant times the derivative:

   $$\frac{d}{dx}[c \cdot f(x)] = c \cdot \frac{d}{dx}f(x)$$

These properties allow us to differentiate complex expressions by breaking them into simpler parts, differentiating each part separately, and then combining the results.