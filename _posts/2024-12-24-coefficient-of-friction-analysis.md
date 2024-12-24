---
layout: post
title: "Calculating the Coefficient of Friction Between a Block and a Table"
date: 2024-12-24
categories: [Classical Mechanics, Physics]
tags: [friction, kinematics, kinetics, force analysis]
math: true
description: "Using two approaches—kinematics and kinetics—to calculate the coefficient of friction for a system involving two identical blocks."
---

## Problem Statement

To determine the coefficient of friction $\mu$ between a block and a horizontal table, consider the following setup: Two identical blocks of mass $m$ are used. One block is placed on a horizontal table, while the other is suspended off the edge, connected by a string. The system starts from rest with both blocks at the same height $h$. When the hanging block falls to the floor, the block on the table slides an additional distance of $x = 2h$ before coming to a complete stop. Based on this information, calculate $\mu$.

---

## Approach 1: Using Kinematics

### Hanging Block (Vertical Motion)

For the hanging block, the equation of motion is:

$$
\sum F_y = m a_y \Rightarrow m g - F_T = m a_y
$$

Where:
- $F_T$ is the tension in the string,
- $a_y$ is the acceleration of the block.

### Table Block (Horizontal Motion)

For the block on the table:

$$
\sum F_x = m a_x \Rightarrow F_T - \mu m g = m a_x
$$

Equating the accelerations (\(a = a_x = a_y\)) for the two blocks:

$$
\begin{aligned}
&\text{Hanging block: } m g - F_T = m a, \\
&\text{Table block: } F_T - \mu m g = m a.
\end{aligned}
$$

Adding the equations:

$$
m g - \mu m g = 2 m a \Rightarrow a = \frac{1}{2} g (1 - \mu)
$$

---

### Final Velocity After Falling Height $h$

Using the kinematic equation for the falling block:

$$
v_h^2 = v_i^2 + 2 a \Delta x \Rightarrow v_h^2 = 0 + 2 \left(\frac{1}{2} g (1 - \mu)\right) h
$$

$$
v_h = \sqrt{g h (1 - \mu)}
$$

---

### Deceleration on the Table After the Hanging Block Hits the Ground

Once the hanging block hits the ground, the block on the table decelerates due to friction. The equation of motion is:

$$
\sum F_x = m a_x \Rightarrow -\mu m g = m a_x \Rightarrow a_x = -\mu g
$$

Using the kinematic equation for the sliding block:

$$
0 = v_h^2 + 2 a \Delta x \Rightarrow 0 = g h (1 - \mu) + 2 (-\mu g) (2h)
$$

Simplifying:

$$
0 = g h (1 - \mu) - 4 \mu g h \Rightarrow 0 = g h (1 - 5 \mu)
$$

Solving for \(\mu\):

$$
\mu = \frac{1}{5}
$$

---

## Approach 2: Using Kinetics

### First Stage (Falling Height $h$)

The work-energy principle for the falling block and sliding block combined:

$$
W_f = \Delta E \Rightarrow -f h = (K_f + U_f) - (K_i + U_i)
$$

$$
-k \mu m g h = \left(\frac{1}{2} m v_h^2 + \frac{1}{2} m v_h^2 + m g h\right) - \left(0 + m g h + m g h\right)
$$

Simplifying:

$$
-k \mu m g h = m v_h^2 - m g h
$$

Using \(v_h^2 = g h (1 - \mu)\):

$$
-k \mu m g h = m \left[g h (1 - \mu)\right] - m g h
$$

---

### Second Stage (Sliding Distance $2h$)

For the sliding block, the work-energy principle is:

$$
W_f = \Delta E \Rightarrow -f (2h) = (K_f + U_f) - (K_i + U_i)
$$

$$
-2 \mu m g h = \left(0 + m g h\right) - \left(\frac{1}{2} m v_h^2 + m g h\right)
$$

Substituting \(v_h^2 = g h (1 - \mu)\):

$$
-2 \mu m g h = -\frac{1}{2} m g h (1 - \mu)
$$

Simplifying:

$$
\mu = \frac{1}{5}
$$

---

## Conclusion

Using both kinematics and kinetics, we find that the coefficient of friction is:

$$
\mu = \frac{1}{5}
$$

This consistent result demonstrates how energy principles and force analysis can complement each other in solving physics problems.
