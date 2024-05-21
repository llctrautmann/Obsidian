---
title: Complex Number Conversion
date: 28-07-2023
time: 16:29
author: Luca Trautmann
tags: []
series:
chapter: 
---

# Conversion of Complex Numbers: Cartesian to Polar Coordinates and Vice Versa

Complex numbers are a crucial mathematical concept used across various fields, including engineering, physics, and computer science. In this post, we will discuss how to convert complex numbers from Cartesian to Polar representation and vice versa, with a special emphasis on its implementation in PyTorch, a popular deep learning library.

## Complex Numbers

A complex number is a number of the form $z = x + iy$, where $x$ and $y$ are real numbers, and $i$ is the imaginary unit with the property $i^2 = -1$. Here, $x$ is the real part and $y$ is the imaginary part of the complex number.

## Cartesian and Polar Representation

A complex number can be represented in two primary ways: Cartesian form ($x + iy$) and polar form ($r(\cos \theta + i \sin \theta)$), where:

- Cartesian Form: $z = x + iy$
- Polar Form: $z = r(\cos \theta + i \sin \theta)$

Here, $r$ is the magnitude (or modulus) of the complex number, and $\theta$ is the phase (or argument).

## Conversion from Cartesian to Polar

If you have a complex number in Cartesian form, $z = x + iy$, you can convert it to polar form as follows:

- Magnitude: $r = \sqrt{x^2 + y^2}$
- Phase: $\theta = \tan^{-1}\left(\frac{y}{x}\right)$

## Conversion from Polar to Cartesian

Conversely, if you have a complex number in polar form, $z = r(\cos \theta + i \sin \theta)$, it can be converted to Cartesian form as:

- Real part: $x = r \cos \theta$
- Imaginary part: $y = r \sin \theta$

## Implementing in PyTorch

In PyTorch, complex numbers can be manipulated easily with a few lines of code. Let's consider a function `replace_magnitude`:

```python
def replace_magnitude(x, mag):
    phase = torch.atan2(x[:, 1:], x[:, :1])  # imag, real
    return torch.cat([mag * torch.cos(phase), mag * torch.sin(phase)], dim=1)
```

This function takes two inputs: a tensor `x` representing complex numbers and a tensor `mag` representing magnitudes. It calculates the phase from `x`, and then creates a new tensor with the same phase but replaced magnitude. Here, `x` is assumed to have the real and imaginary parts of complex numbers as its first and second channels, respectively.

It's important to note that in PyTorch, the `torch.complex()` function can be used to create a complex tensor from two real-valued tensors representing the real and imaginary parts. However, as of the time of writing this post (September 2021), complex number support in PyTorch is still being enhanced, and some operations may behave differently in newer versions of the library.

## Conclusion

Complex numbers are fascinating and versatile mathematical constructs. Their conversion between Cartesian and polar coordinates forms a fundamental part of the understanding and manipulation of these numbers. Although we've used PyTorch for the implementation in this post, similar concepts apply across various mathematical and programming contexts.

---

I hope you find this post informative and helpful. Please remember to check the PyTorch documentation and keep abreast with the latest updates as the complex number support continues to improve.










# Chapters
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```