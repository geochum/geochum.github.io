---
layout: post
title: "Analyzing the James Webb Space Telescope's Orbit"
date: 2025-01-20
categories: [Astrophysics, Orbital Mechanics]
tags: [gravitational physics, orbital motion, telescope]
math: true
description: "A detailed analysis of the James Webb Space Telescope's orbit using gravitational physics and approximations."
---

## Problem Statement

The James Webb Space Telescope (JWST) orbits in a unique configuration, maintaining its position along the Sun-Earth line, farther from the Sun than the Earth. In a simplified model:

- Assume the **Earth** is in a circular orbit around the **Sun** with a period $T = 365 \, \text{days}$.
- The **Sun** has a mass $M$ much greater than the mass of the **Earth** $m$, which is itself much greater than the mass of the **telescope** $\mu$.
- The distance between the Sun and the Earth is $L$, and the distance between the Earth and the telescope is $x$.
- It is given that $x \ll L$.

### Tasks

1. **(a)** Derive a formula for the mass of the Earth $m$, expressed in terms of the gravitational constant $G$, the gravitational acceleration at the surface of the Earth $g$, and the radius of the Earth $R$.
2. **(b)** Derive a formula for $x$, expressed in terms of $G$, $m$, and $T$, using appropriate approximations for small values of $x/L$.
3. **(c)** Transform the formula for $x$ to express it in terms of $T$, $g$, and $R$.

---

## Solution

### (a) Derive the Mass of the Earth

At the Earth's surface, the gravitational field strength $g$ is related to the Earth's mass $m$ by:

$$
g = \frac{G m}{R^2}.
$$

Rearranging for $m$:

$$
m = \frac{g R^2}{G}.
$$

This provides a relationship between $g$, $R$, $G$, and $m$.

---

### (b) Derive a Formula for $x$ in Terms of $G$, $m$, and $T$

#### Gravitational Forces and Accelerations

We analyze the forces acting on the telescope and the Earth, assuming circular orbits.

1. **Earth's Orbit**:
   The gravitational force acting on the Earth due to the Sun provides the centripetal force for its circular motion:

   $$
   \frac{G M m}{L^2} = m \frac{v_m^2}{L},
   $$

   where $v_m$ is the orbital speed of the Earth. Substituting $v_m = \frac{2 \pi L}{T}$:

   $$
   \frac{G M}{L^2} = \frac{4 \pi^2 L}{T^2}.
   $$

   This implies:

   $$
   \frac{G M}{L^3} = \frac{4 \pi^2}{T^2}.
   $$

#### Why Neglect the Telescope’s Gravitational Force?

The telescope exerts a gravitational force on the Earth, given by:

$$
F_{\text{telescope}} = \frac{G m \mu}{x^2}.
$$

However, since \(\mu\) (the telescope's mass) is negligible compared to \(M\) (the Sun's mass) and \(m\) (the Earth's mass), its gravitational contribution is much smaller than the gravitational force from the Sun:

$$
\frac{F_{\text{telescope}}}{F_{\text{Sun}}} = \frac{\frac{G m \mu}{x^2}}{\frac{G M m}{L^2}} = \frac{\mu L^2}{M x^2}.
$$

For typical values (\(\mu \ll m\), \(x \ll L\)), this ratio is extremely small, justifying the exclusion of the telescope’s gravitational force from the analysis of the Earth’s orbit.

---

2. **Telescope's Orbit**:
   The telescope experiences gravitational forces from both the Sun and the Earth. The net radial force is:

   $$
   \frac{G M \mu}{(L+x)^2} + \frac{G m \mu}{x^2} = \mu \frac{v_\mu^2}{L+x},
   $$

   where $v_\mu$ is the orbital speed of the telescope. Substituting $v_\mu = \frac{2 \pi (L+x)}{T}$:

   $$
   \frac{G M}{(L+x)^2} + \frac{G m}{x^2} = \frac{4 \pi^2 (L+x)}{T^2}.
   $$

---

#### Approximations for Small $x/L$

Given $x \ll L$, approximate terms as follows:
- $\frac{1}{(L+x)^2} \approx \frac{1}{L^2} \left(1 - \frac{2x}{L}\right) = \frac{1}{L^2} - \frac{2x}{L^3}$.

Substituting into $\frac{G M}{(L+x)^2}$:

$$
\frac{G M}{(L+x)^2} \approx \frac{G M}{L^2} - \frac{2 G M x}{L^3}.
$$

Expanding $\frac{4 \pi^2 (L+x)}{T^2}$ exactly:

$$
\frac{4 \pi^2 (L+x)}{T^2} = \frac{4 \pi^2 L}{T^2} + \frac{4 \pi^2 x}{T^2}.
$$

Using these results:

$$
\frac{G M}{L^2} - \frac{2 G M x}{L^3} + \frac{G m}{x^2} = \frac{4 \pi^2 L}{T^2} + \frac{4 \pi^2 x}{T^2}.
$$

Equating the leading terms:

$$
\frac{G M}{L^2} = \frac{4 \pi^2 L}{T^2}.
$$

Substituting this result:

$$
- \frac{2 G M x}{L^3} + \frac{G m}{x^2} = \frac{4 \pi^2 x}{T^2}.
$$

Simplifying further:

$$
\frac{G m}{x^2} = \frac{4 \pi^2 x}{T^2} + \frac{2 G M x}{L^3}.
$$

Since $\frac{G M}{L^3} = \frac{4 \pi^2}{T^2}$:

$$
\frac{G m}{x^2} = \frac{4 \pi^2 x}{T^2} + \frac{8 \pi^2 x}{T^2}.
$$

Combining terms:

$$
\frac{G m}{x^2} = \frac{12 \pi^2 x}{T^2}.
$$

Rearranging for $x$:

$$
x^3 = \frac{G m T^2}{12 \pi^2}.
$$

Thus:

$$
x = \sqrt[3]{\frac{G m T^2}{12 \pi^2}}.
$$

---

### (c) Transform $x$ in Terms of $T$, $g$, and $R$

Substitute $m = \frac{g R^2}{G}$ into the formula for $x$:

$$
x^3 = \frac{G \left(\frac{g R^2}{G}\right) T^2}{12 \pi^2}.
$$

Simplify:

$$
x^3 = \frac{g R^2 T^2}{12 \pi^2}.
$$

Thus:

$$
x = \sqrt[3]{\frac{g R^2 T^2}{12 \pi^2}}.
$$

---

## Final Results

1. **Mass of the Earth**:
   $$
   m = \frac{g R^2}{G}.
   $$

2. **Distance $x$ in Terms of $G$, $m$, and $T$**:
   $$
   x = \sqrt[3]{\frac{G m T^2}{12 \pi^2}}.
   $$

3. **Distance $x$ in Terms of $T$, $g$, and $R$**:
   $$
   x = \sqrt[3]{\frac{g R^2 T^2}{12 \pi^2}}.
   $$

---

## Conclusion

This analysis rigorously justifies why the telescope’s gravitational influence is negligible when considering the Earth’s orbit. It also demonstrates how approximations and gravitational physics can provide insight into the James Webb Space Telescope’s stable position in the Sun-Earth system.
