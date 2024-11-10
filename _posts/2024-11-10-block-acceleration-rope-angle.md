---
layout: post
title: "Effects of Rope Angle on Block Acceleration"
date: 2024-11-10
categories: [Classical Mechanics]
tags: [friction, force, acceleration, physics]
math: true
description: "Exploring the effects of varying the angle of a pulling force on a block, friction, and acceleration."
---

## Problem Statement

A block of mass $M$ is pulled by a rope that makes an angle $\theta$ above the horizontal. The coefficient of kinetic friction between the block and floor is $\mu$.

The block is initially at rest and starts accelerating to the right along the floor.

**(a)** Briefly explain why slightly increasing the angle $\theta$ (without changing the magnitude of the force exerted by the rope) could cause a decrease in the block's acceleration.

**(b)** Suppose the rope is pulled with a force that has a magnitude that is one-third the weight of the block, or $\frac{M g}{3}$. In this case, when the block accelerates, its acceleration is 

$$
a = g \left( \frac{1}{3} \cos \theta + \frac{\mu}{3} \sin \theta - \mu \right).
$$

Explain why the above equation is consistent with the claim that an increase in the angle $\theta$ could cause a decrease in the acceleration.

## Solution

### (a)

Let the $+x$-direction point rightwards and the $+y$-direction point upwards.

**Force equation in the $x$-direction:**

$$
\sum F_x = M a_x \Rightarrow -f_k + F_R \cos(\theta) = M a \Rightarrow a = \frac{-\mu F_n + F_R \cos(\theta)}{M}
$$

**Force equation in the $y$-direction:**

$$
\sum F_y = M a_y \Rightarrow F_n + F_R \sin(\theta) - M g = 0 \Rightarrow F_n = M g - F_R \sin(\theta)
$$

Substituting for $F_n$ in the $x$-direction equation:

$$
a = \frac{-\mu (M g - F_R \sin(\theta)) + F_R \cos(\theta)}{M} = \frac{-\mu M g + \mu F_R \sin(\theta) + F_R \cos(\theta)}{M} = \frac{F_R}{M} (\mu \sin(\theta) + \cos(\theta)) - \mu g
$$

Using the identity: $\sin(A + B) = \sin(A) \cos(B) + \cos(A) \sin(B)$

Let $A = \theta$, $\cos(B) = \mu$, and $\sin(B) = 1$. Then we have $\sin(\theta + B) = \mu \sin(\theta) + \cos(\theta)$.

Now,

$$
\frac{\sin(B)}{\cos(B)} = \frac{1}{\mu} \Rightarrow \tan(B) = \frac{1}{\mu} \Rightarrow B = \arctan\left(\frac{1}{\mu}\right)
$$

where $\arctan\left(\frac{1}{\mu}\right) > 0$ since $\mu > 0$.

Thus, we have:

$$
\mu \sin(\theta) + \cos(\theta) = \sin\left(\theta + \arctan\left(\frac{1}{\mu}\right)\right)
$$

This represents a shifted sine curve that is shifted to the left by $\arctan\left(\frac{1}{\mu}\right)$.

Therefore, when $\theta > 90^\circ - \arctan\left(\frac{1}{\mu}\right)$, the acceleration will begin to decrease, as this is when $\sin\left(\theta + \arctan\left(\frac{1}{\mu}\right)\right)$ starts to decrease.

### (b)

We are given that the rope is pulled with a force $F = \frac{M g}{3}$. Thus,

$$
a = \frac{M g}{3 M} (\mu \sin(\theta) + \cos(\theta)) - \mu g = \frac{g}{3} (\mu \sin(\theta) + \cos(\theta)) - \mu g = g \left(\frac{1}{3} (\mu \sin(\theta) + \cos(\theta)) - \mu\right)
$$

As we've shown earlier, $\mu \sin(\theta) + \cos(\theta) = \sin\left(\theta + \arctan\left(\frac{1}{\mu}\right)\right)$. So, 

$$
a = \frac{1}{3} g \sin\left(\theta + \arctan\left(\frac{1}{\mu}\right)\right) - \mu g
$$

But $\mu g$ and $\frac{1}{3} g$ are just constants, so they do not affect the overall behavior of the acceleration as $\theta$ increases.

As we've mentioned before, $\sin\left(\theta + \arctan\left(\frac{1}{\mu}\right)\right)$ increases at first for $0^\circ \leq \theta \leq 90^\circ - \arctan\left(\frac{1}{\mu}\right)$. Then it decreases when $\theta > 90^\circ - \arctan\left(\frac{1}{\mu}\right)$.
