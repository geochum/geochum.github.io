---
layout: post
title: Forces on a Motorcycle on a Vertical Circular Track
date: 2024-11-05
categories: [Classical Mechanics]
tags: [circular motion, forces, friction]
math: true
description: "A look at the forces acting on a motorcycle moving on a vertical circular track and the conditions necessary for successful completion of the stunt."
---

## Problem Statement

A 250 kg motorcycle is driven around a 12-meter tall vertical circular track at a constant speed of $11 \, \mathrm{m/s}$.

**Find:**
1. The normal and friction forces at four points on the track:
   - (i) at the bottom (and rising)
   - (ii) halfway to the top
   - (iii) at the top
   - (iv) $45^{\circ}$ past the top
2. The minimum coefficient of static friction needed to complete the stunt as planned.

*Assumptions:* The mass of the motorcycle includes the mass of the rider. Aerodynamic drag and rolling resistance are negligible.

## Given Data

- Mass of motorcycle and rider, $m = 250 \, \mathrm{kg}$
- Track height, $H = 12 \, \mathrm{m}$
- Speed, $v = 11 \, \mathrm{m/s}$
- Radius of the track, $R = H/2 = 6 \, \mathrm{m}$

## Solution

### (a) Normal and Friction Forces at Key Points

#### (i) At the Bottom (Rising)

- **Radial direction:** Let the $+r$ direction point towards the center of the track.

$$
\sum F_r = F_n - F_g = m \frac{v^2}{R}
$$

Rearranging, we get:

$$
F_n = m \frac{v^2}{R} + mg
$$

- **Tangential direction:** Let the $+x$ direction point left.

$$
\sum F_x = -F_f = m \cdot 0 \Rightarrow F_f = 0
$$

Since the motorcycle moves at constant speed, $a_x = 0$, so $F_f = 0$.

#### (ii) Halfway to the Top

- **Radial direction:** $+r$ direction points towards the center.

$$
\sum F_r = F_n = m \frac{v^2}{R}
$$

Thus:

$$
F_n = m \frac{v^2}{R}
$$

- **Vertical direction:** Let the $+y$ direction point upwards.

$$
\sum F_y = F_f - F_g = m \cdot 0 \Rightarrow F_f = mg
$$

Since $a_y = 0$ at constant speed, $F_f = mg$.

#### (iii) At the Top

- **Radial direction:** $+r$ direction points towards the center.

$$
\sum F_r = F_n + F_g = m \frac{v^2}{R}
$$

Solving for $F_n$:

$$
F_n = m \frac{v^2}{R} - mg
$$

- **Tangential direction:** Let the $+x$ direction point right.

$$
\sum F_x = -F_f = m \cdot 0 \Rightarrow F_f = 0
$$

Since $a_x = 0$, $F_f = 0$.

#### (iv) $45^{\circ}$ Past the Top

- **Radial direction:** $+r$ direction points towards the center.

$$
\sum F_r = F_n + F_g \cos(45^{\circ}) = m \frac{v^2}{R}
$$

Thus:

$$
F_n = m \frac{v^2}{R} - mg \cos(45^{\circ})
$$

- **Tangential direction:** $+x$ direction points tangentially down at $45^{\circ}$.

$$
\sum F_x = -F_f + F_g \sin(45^{\circ}) = m \cdot 0 \Rightarrow F_f = mg \sin(45^{\circ})
$$

Since $a_x = 0$, $F_f = mg \sin(45^{\circ})$.

### (b) Minimum Coefficient of Static Friction

From case (ii), we require $F_f \geq mg$ for the motorcycle to stay on the track. Since $F_f \leq \mu F_n$ and $F_n = m \frac{v^2}{R}$ (from case ii), we have:

$$
mg \leq F_f \leq \mu m \frac{v^2}{R}
$$

Solving for $\mu$:

$$
\mu \geq \frac{mg}{m \frac{v^2}{R}} = \frac{Rg}{v^2}
$$

Thus, the minimum coefficient of static friction is:

$$
\mu \geq \frac{Rg}{v^2}
$$
