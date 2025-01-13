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

When a ball with a mass of $3 \, \text{kg}$ is pushed at an angle to the horizontal, $220 \, \text{J}$ of work is done on it before launch. The ball reaches the highest point of its trajectory with a kinetic energy of $165 \, \text{J}$. At what angle was the ball launched?

---

## Approach

We use the following key principles and equations:

1. **Horizontal Speed at the Top**:
   At the highest point of the trajectory, the kinetic energy is entirely due to the horizontal velocity:

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

   Substituting for $v_{\text{launch}, y}$ and $v_{\text{top}}$:

   $$
   \theta_{\text{launch}} = \arctan\left(\sqrt{\frac{W_{\text{net}} - K_{\text{top}}}{K_{\text{top}}}}\right)
   $$

---

## Solution

### Step 1: Calculate $v_{\text{top}}$
Given $K_{\text{top}} = 165 \, \text{J}$ and $m = 3 \, \text{kg}$:

$$
v_{\text{top}} = \sqrt{\frac{2 K_{\text{top}}}{m}} = \sqrt{\frac{2 \cdot 165}{3}} = \sqrt{110} \approx 10.49 \, \text{m/s}
$$

---

### Step 2: Calculate $v_{\text{launch}}$
Given $W_{\text{net}} = 220 \, \text{J}$ and $m = 3 \, \text{kg}$:

$$
v_{\text{launch}} = \sqrt{\frac{2 W_{\text{net}}}{m}} = \sqrt{\frac{2 \cdot 220}{3}} = \sqrt{\frac{440}{3}} \approx 12.12 \, \text{m/s}
$$

---

### Step 3: Calculate $v_{\text{launch}, y}$
The vertical component of the launch velocity is:

$$
v_{\text{launch}, y} = \sqrt{v_{\text{launch}}^2 - v_{\text{top}}^2}
$$

Substitute $v_{\text{launch}} \approx 12.12 \, \text{m/s}$ and $v_{\text{top}} \approx 10.49 \, \text{m/s}$:

$$
v_{\text{launch}, y} = \sqrt{12.12^2 - 10.49^2} = \sqrt{146.95 - 110.05} = \sqrt{36.90} \approx 6.07 \, \text{m/s}
$$

---

### Step 4: Calculate $\theta_{\text{launch}}$
The launch angle is:

$$
\theta_{\text{launch}} = \arctan\left(\frac{v_{\text{launch}, y}}{v_{\text{top}}}\right)
$$

Substitute $v_{\text{launch}, y} \approx 6.07 \, \text{m/s}$ and $v_{\text{top}} \approx 10.49 \, \text{m/s}$:

$$
\theta_{\text{launch}} = \arctan\left(\frac{6.07}{10.49}\right) = \arctan\left(0.5788\right) \approx 30^\circ
$$

---

## Final Answer

The launch angle of the ball is:

$$
\boxed{30^\circ}
$$

---

## Conclusion

This problem illustrates how the principles of work, energy, and projectile motion can be combined to determine the launch angle of a projectile. The step-by-step approach provides insight into the relationship between kinetic energy, velocity components, and the trajectory of the ball.
