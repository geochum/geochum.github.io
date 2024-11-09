---
layout: post
title: "Evaluating a Cubic Function with Specific Extrema"
date: 2024-11-09
categories: [Calculus]
tags: [cubic functions, calculus, extrema, integration]
math: true
description: "Discover how to evaluate a cubic function and its derived function based on given extrema conditions. We solve for a scaled output of the function with a practical approach to calculus concepts."
---

## Problem Statement

Let $ f(x) $ be a cubic function with a leading coefficient of $ 1 $, given by

$$
f(x) = x^3 + b x^2 + c x + d.
$$

We define a function $ g(x) $ as

$$
g(x) = \int_0^x f'(t + a) f'(t - a) \, dt,
$$

and we know that $ g(x) $ has local extrema only at $ x = \frac{1}{2} $ and $ x = \frac{13}{2} $.

Given that $ f(0) = -\frac{1}{2} $, find the value of $ a f(1) $.

## Solution

Since $ f(x) = x^3 + b x^2 + c x + d $, the derivative of $ f(x) $ is

$$
f'(x) = 3x^2 + 2b x + c.
$$

Now, differentiating $ g(x) $ with respect to $ x $ gives

$$
g'(x) = f'(x + a) f'(x - a).
$$

### Analyzing $ g'(x) $ and the Properties of $ f'(x) $

Since $ g(x) $ has only two local extrema, $ g'(x) $ must have exactly two zeros. This implies that $ f'(x) $, a quadratic function, should have exactly two distinct real zeros to produce two zeros in $ g'(x) $ when evaluated as $ f'(x + a) f'(x - a) $. Thus, we set $ f'(x) = 0 $ and solve for its roots:

$$
f'(x) = 3x^2 + 2b x + c = 0.
$$

Solving this quadratic equation, we find

$$
x = \frac{-2b \pm \sqrt{4b^2 - 12c}}{6} = -\frac{b}{3} \pm \frac{\sqrt{b^2 - 3c}}{3}.
$$

To ensure $ g'(x) $ has exactly two zeros, we align the zeros of $ f'(x + a) $ and $ f'(x - a) $ such that the larger zero of $ f'(x + a) $ coincides with the smaller zero of $ f'(x - a) $. For this alignment, we require:

$$
a = \frac{\sqrt{b^2 - 3c}}{3}.
$$

### Using Symmetry to Solve for $ b $

Since $ g(x) $ has extrema at $ x = \frac{1}{2} $ and $ x = \frac{13}{2} $, the midpoint of these extrema corresponds to the vertex of $ f'(x) $, which is at $ x = -\frac{b}{3} $. So,

$$
\frac{\frac{1}{2} + \frac{13}{2}}{2} = -\frac{b}{3},
$$

yielding

$$
b = -\frac{21}{2}.
$$

### Solving for $ a $ and $ c $

For the larger zero of $ g'(x) $, which aligns with the larger zero of $ f'(x - a) $, we have

$$
\frac{13}{2} = a - \frac{b}{3} + \frac{\sqrt{b^2 - 3c}}{3}.
$$

Simplifying, we find

$$
a = \frac{3}{2}.
$$

For $ c $, we substitute $ a = \frac{3}{2} $ back into our expression:

$$
a = \frac{\sqrt{b^2 - 3c}}{3} \Rightarrow c = -\frac{9a^2 - b^2}{3} = 30.
$$

### Solving for $ d $

Since $ f(0) = -\frac{1}{2} $, we have

$$
d = -\frac{1}{2}.
$$

### Final Form of $ f(x) $

Now, we can write $ f(x) $ as

$$
f(x) = x^3 - \frac{21}{2} x^2 + 30 x - \frac{1}{2}.
$$

Then,

$$
f(1) = 1^3 - \frac{21}{2}(1)^2 + 30 \cdot 1 - \frac{1}{2} = 20.
$$

Thus,

$$
a f(1) = \frac{3}{2} \cdot 20 = 30.
$$
