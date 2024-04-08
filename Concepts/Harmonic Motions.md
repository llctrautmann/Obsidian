---
title: Harmonic Motions
date: 15-08-2023
time: 17:17
author: Luca Trautmann
tags: []
series: "Signal Processing"
chapter: 0
---

> [!Chapters]-
> ```dataview
> TABLE chapter as Chapter
> FROM "concepts"
> WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
> SORT chapter asc
> ```

# Harmonic Motions
# Understanding Simple Harmonic Motion (SHM)

Simple Harmonic Motion (SHM) is a fascinating phenomenon observed in certain systems where an object oscillates around a central equilibrium position. In this post, we'll delve into the key characteristics that define SHM and explore its intriguing nature.

## What is Simple Harmonic Motion?

At its core, SHM is a type of periodic motion where an object repetitively moves back and forth around a central or equilibrium position. It can be visualized in everyday systems such as a swinging pendulum or a mass attached to a spring.

Two fundamental attributes define SHM:

1. **Acceleration is Proportional to Displacement**: This means that the further you displace the object from its equilibrium, the greater the acceleration it will experience when trying to return to its original position. This relationship can be mathematically expressed as: �=−�2�a=−ω2x Here, �a is the acceleration, �ω is the angular frequency of the motion, and �x is the displacement from the equilibrium position.
    
2. **Acceleration is Always Directed Toward the Equilibrium Position**: No matter in which direction you displace the object, the resulting force and acceleration will always try to push or pull it back to its equilibrium or rest position. Essentially, the system has an innate tendency to restore balance.
    

## Everyday Examples

Let's look at two common systems that exhibit SHM to better understand these properties:

- **Spring-Mass System**: A mass attached to a spring will oscillate when the spring is stretched or compressed and then released. The further you stretch or compress the spring, the stronger the force (and thus, the acceleration) will be when you let go. In every scenario, the spring will try to return to its original length, which is its equilibrium position.
    
- **Simple Pendulum**: When you displace a pendulum from its resting position and let go, it swings back and forth, trying to return to its original hanging position. Whether you move it to the left or right, it always swings back towards the center.
    

## Wrapping Up

SHM is a captivating topic that elegantly combines geometry, physics, and mathematics. By understanding its defining characteristics and observing its properties in everyday systems, we gain insight into the harmonic rhythms of the world around us. Whether it's the tick-tock of a grandfather clock or the rhythmic bouncing of a diving board, SHM plays a foundational role in the movements we observe daily.


 
 At instant, $t$, the projection, $P$, has a displacement, velocity, and acceleration given by (1), (2), and (3) respectively:
$$
\begin{aligned}
s(t) & =a_0 \cos \theta=a_0 \cos \omega t \\
s^{\prime}(t) & =-a_0 \omega \sin \omega t \\
s^{\prime \prime}(t) & =-a_0 \omega^2 \cos \omega t \\
& =-\omega^2 s(t)
\end{aligned}
$$
where the primes indicate the order of derivative. We can relate the frequency, $f=\omega / 2 \pi$, to displacement by solving differential equation (3). The solution is $z(t)$ given by
$$
z(t)=\alpha e^{j 2 \pi f t}
$$
where $\omega=2 \pi f$ is a uniform angular speed and $\alpha$ is an arbitrary constant. Equations (1)-(4) relate the concept of frequency to a practical example.








