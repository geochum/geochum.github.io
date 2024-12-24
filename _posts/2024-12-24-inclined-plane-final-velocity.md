---
layout: post
title: "Sliding Up and Down an Inclined Plane: Finding the Final Velocity"
date: 2024-12-24
categories: [Classical Mechanics, Physics]
tags: [inclined plane, friction, velocity, kinematics]
math: true
description: "A body slides up and down an inclined plane. How fast is it moving when it returns to its starting point?"
---

## Problem Statement

A body is given an initial velocity $v_0 = 8 \, \text{m/s}$ and slides **up an inclined plane** with an incline angle of $\theta = 30^\circ$. After traveling a distance of $L = 5 \, \text{m}$, it comes to a stop and begins sliding **back down** the incline. The goal is to calculate the velocity of the object when it returns to its initial position. The final answer is $v_f = 6 \, \text{m/s}$.

---

## Approach

We'll solve this problem by analyzing the motion in two stages: 

1. **Up the incline**: Determine the deceleration and find the coefficient of friction $\mu$.
2. **Down the incline**: Use the coefficient of friction to find the acceleration and final velocity.

---

### Stage 1: Motion Up the Incline

As the object slides up, it experiences deceleration due to gravity and friction. The forces acting on the object are:

- The component of gravity along the incline: $F_g = m g \sin(\theta)$,
- The frictional force: $f = \mu F_N = \mu m g \cos(\theta)$,
- The net force along the incline: $F_\text{net} = -m g \sin(\theta) - \mu m g \cos(\theta)$.

Using Newton's second law:

$$
\sum F_x = m a_x \Rightarrow -m g \sin(\theta) - \mu m g \cos(\theta) = m a_x
$$

Simplifying:

$$
a_x = -g (\mu \cos(\theta) + \sin(\theta))
$$

Now, using the kinematic equation for velocity and distance:

$$
v_f^2 = v_0^2 + 2 a_x \Delta x
$$

At the top of the incline, the object stops ($v_f = 0$), so:

$$
0 = v_0^2 + 2 \left(-g (\mu \cos(\theta) + \sin(\theta))\right) L
$$

Rearranging to solve for $\mu$:

$$
\mu = \frac{v_0^2}{2 g L \cos(\theta)} - \tan(\theta)
$$

---

### Stage 2: Motion Down the Incline

As the object slides back down, friction opposes the motion. The forces along the incline are:

- The component of gravity along the incline: $F_g = m g \sin(\theta)$,
- The frictional force (opposing motion): $f = \mu m g \cos(\theta)$,
- The net force along the incline: $F_\text{net} = m g \sin(\theta) - \mu m g \cos(\theta)$.

Using Newton's second law:

$$
\sum F_x = m a_x \Rightarrow m g \sin(\theta) - \mu m g \cos(\theta) = m a_x
$$

Simplifying:

$$
a_x = g (\sin(\theta) - \mu \cos(\theta))
$$

Using the kinematic equation again for velocity and distance:

$$
v_f^2 = v_0^2 + 2 a_x \Delta x
$$

The object starts at rest when sliding back down ($v_0 = 0$), so:

$$
v_f^2 = 2 g (\sin(\theta) - \mu \cos(\theta)) (-L)
$$

Substituting $\mu$ from Stage 1:

$$
\mu = \frac{v_0^2}{2 g L \cos(\theta)} - \tan(\theta)
$$

Gives:

$$
v_f^2 = -2 g L \left(\sin(\theta) - \left(\frac{v_0^2}{2 g L \cos(\theta)} - \tan(\theta)\right) \cos(\theta)\right)
$$

Simplifying:

$$
v_f^2 = v_0^2 - 4 g L \sin(\theta)
$$

Taking the square root:

$$
v_f = \sqrt{v_0^2 - 4 g L \sin(\theta)}
$$

---

### Final Calculation

Given:

- $v_0 = 8 \, \text{m/s}$,
- $L = 5 \, \text{m}$,
- $\theta = 30^\circ$,
- $g = 9.8 \, \text{m/s}^2$,

Substitute values into the equation:

$$
v_f = \sqrt{8^2 - 4 (9.8) (5) \sin(30^\circ)}
$$

$$
v_f = \sqrt{64 - 4 (9.8) (5) (0.5)}
$$

$$
v_f = \sqrt{64 - 98} = \sqrt{36} = 6 \, \text{m/s}
$$

---

## Conclusion

The object's velocity when it returns to its starting point is:

$$
v_f = 6 \, \text{m/s}
$$

This problem demonstrates the interplay of forces on an inclined plane and how energy dissipation due to friction influences motion.
