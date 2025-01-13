---
layout: post
title: "Calculating the Launch Angle of a Thrown Ball"
date: 2025-01-12
categories: [Classical Mechanics, Physics]
tags: [work, kinetic energy, launch angle, projectile motion]
math: true
description: "Determining the launch angle of a ball given the work done on it and its kinetic energy at the highest point of the trajectory."
---

## Problem Statement

A ball with mass $m = 3 \, \text{kg}$ is pushed at an angle to the horizontal, and $W_{\text{net}} = 220 \, \text{J}$ of work is done on it before launch. At the highest point of its trajectory, the ball's kinetic energy is $K_{\text{top}} = 165 \, \text{J}$. Determine the launch angle $\theta_{\text{launch}}$ of the ball.

---

## Approach

We use the following principles and equations:

1. **Horizontal Speed at the Top**:
   At the highest point of the trajectory, the ball's kinetic energy is entirely due to its horizontal velocity:

   $$
   K_{\text{top}} = \frac{1}{2} m v_{\text{top}}^2 \quad \Rightarrow \quad v_{\text{top}} = \sqrt{\frac{2 K_{\text{top}}}{m}}
   $$

2. **Launch Speed**:
   The total work done on the ball before launch is converted into its kinetic energy at launch:

   $$
   W_{\text{net}} = \Delta K = K_{\text{launch}} - 0 \quad \Rightarrow \quad K_{\text{launch}} = W_{\text{net}}
   $$

   Substituting for $K_{\text{launch}}$:

   $$
   v_{\text{launch}} = \sqrt{\frac{2 W_{\text{net}}}{m}}
   $$

3. **Vertical Component of Launch Speed**:
   The magnitude of the launch velocity $v_{\text{launch}}$ is related to its horizontal and vertical components:

   $$
   v_{\text{launch}}^2 = v_{\text{top}}^2 + v_{\text{launch}, y}^2 \quad \Rightarrow \quad v_{\text{launch}, y} = \sqrt{v_{\text{launch}}^2 - v_{\text{top}}^2}
   $$

4. **Launch Angle**:
   The angle of launch is given by:

   $$
   \theta_{\text{launch}} = \arctan\left(\frac{v_{\text{launch}, y}}{v_{\text{top}}}\right)
   $$

Substituting the expressions for $v_{\text{launch}, y}$ and $v_{\text{top}}$:

$$
\theta_{\text{launch}} = \arctan\left(\sqrt{\frac{v_{\text{launch}}^2 - v_{\text{top}}^2}{v_{\text{top}}^2}}\right)
$$

Simplify further using the relationships for $v_{\text{launch}}$ and $v_{\text{top}}$:

$$
\theta_{\text{launch}} = \arctan\left(\sqrt{\frac{\frac{2 W_{\text{net}}}{m} - \frac{2 K_{\text{top}}}{m}}{\frac{2 K_{\text{top}}}{m}}}\right)
$$

Factor out $\frac{1}{m}$ and simplify:

$$
\theta_{\text{launch}} = \arctan\left(\sqrt{\frac{W_{\text{net}} - K_{\text{top}}}{K_{\text{top}}}}\right)
$$

---

## Solution

Substitute the given values into the final expression:

- $W_{\text{net}} = 220 \, \text{J}$,
- $K_{\text{top}} = 165 \, \text{J}$,

$$
\theta_{\text{launch}} = \arctan\left(\sqrt{\frac{220 - 165}{165}}\right)
$$

Simplify:

$$
\theta_{\text{launch}} = \arctan\left(\sqrt{\frac{55}{165}}\right)
$$

$$
\theta_{\text{launch}} = \arctan\left(\sqrt{\frac{1}{3}}\right)
$$

$$
\theta_{\text{launch}} = \arctan\left(\frac{\sqrt{3}}{3}\right)
$$

Using trigonometric values:

$$
\theta_{\text{launch}} = \frac{\pi}{6} \, \text{radians} \quad \text{or} \quad 30^\circ
$$

---

## Final Answer

The launch angle of the ball is:

$$
\boxed{30^\circ}
$$

---

## Conclusion

This problem demonstrates how energy principles and trigonometric relationships can be used to analyze projectile motion. The symbolic approach highlights the relationships between work, kinetic energy, and velocity components before substituting specific numerical values.
