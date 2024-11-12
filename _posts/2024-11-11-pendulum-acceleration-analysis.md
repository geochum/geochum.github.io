---
layout: post
title: "Analyzing the Acceleration of a Pendulum on the Moon"
date: 2024-11-11
categories: [Classical Mechanics, Physics]
tags: [pendulum, acceleration, moon, forces]
math: true
description: "Exploring the variation in total acceleration and tension force for a pendulum on the Moon released from a horizontal position to vertical."
---

## Problem Statement

Astronauts on the Moon perform an experiment with a simple pendulum that is released from the horizontal position at rest. We are interested in how the total acceleration of the pendulum's mass varies in magnitude and direction as the angle $\theta$ goes from $0^\circ$ to $90^\circ$.

Let $P$ be the pivot point of the pendulum. The forces acting on the bob with mass $m$ as it moves from the horizontal position to vertical are:
- The force of gravity, always pointing downward.
- The tension force $F_T$, always pointing towards $P$.

Let $L$ be the length of the pendulum. 

### Force Analysis in Radial and Tangential Directions

1. **Radial Direction (Towards $P$):**

   We denote the +r-direction as pointing towards $P$. The net force in this direction is:

   $$
   \sum F_r = m a_r \Rightarrow F_T - m g \sin(\theta) = m \frac{v^2}{L}
   $$

   Thus, the tension force $F_T$ is:

   $$
   F_T = m \left( \frac{v^2}{L} + g \sin(\theta) \right)
   $$

2. **Tangential Direction (Along the Motion):**

   We denote the +t-direction as tangential to the direction of motion. The tangential acceleration $a_t$ is given by:

   $$
   \sum F_t = m a_t \Rightarrow m g \cos(\theta) = m a_t \Rightarrow a_t = g \cos(\theta)
   $$

### Velocity and Radial Acceleration Using Conservation of Energy

To find the speed $v$ of the bob as a function of $\theta$, we use conservation of mechanical energy. Assuming the initial point is when the pendulum is at the horizontal position ($\theta = 0^\circ$), and considering the gravitational force as conservative:

$$
\Delta E = 0 \Rightarrow E_f = E_i \Rightarrow m g (L - L \sin(\theta)) + \frac{1}{2} m v^2 = m g L
$$

Solving for $v$, we get:

$$
v = \sqrt{2gL \sin(\theta)}
$$

Then, the radial acceleration $a_r$ becomes:

$$
a_r = \frac{v^2}{L} = 2g \sin(\theta)
$$

### Magnitude of Total Acceleration

The magnitude of the total acceleration is:

$$
\| \vec{a} \| = \sqrt{a_r^2 + a_t^2} = \sqrt{(2g \sin(\theta))^2 + (g \cos(\theta))^2} = \sqrt{g^2 (4 \sin^2(\theta) + \cos^2(\theta))}
$$

### Direction of Total Acceleration

To determine the direction of the total acceleration $\vec{a}$ with respect to the standard coordinate system, we decompose the radial and tangential accelerations into components:

1. **Components of $\vec{a}_r$ in the standard coordinate system**:
 
   $$
   \vec{a}_r = (a_r \cos(\theta), a_r \sin(\theta)) = (2g \sin(\theta) \cos(\theta), 2g \sin(\theta) \sin(\theta))
   $$

2. **Components of $\vec{a}_t$ in the standard coordinate system**:

   $$
   \vec{a}_t = (a_t \sin(\theta), -a_t \cos(\theta)) = (g \cos(\theta) \sin(\theta), -g \cos(\theta) \cos(\theta))
   $$

Thus, the total acceleration $\vec{a}$ has components:

$$
\vec{a} = \vec{a}_r + \vec{a}_t = (3g \sin(\theta) \cos(\theta), -\frac{1}{2} g (3 \cos(2\theta) - 1))
$$

Let $\phi$ be the direction of the total acceleration:

$$
\phi = \arctan\left(\frac{a_y}{a_x}\right) = \arctan\left(\frac{-(1/2) g (3 \cos(2\theta) - 1)}{3 g \sin(\theta) \cos(\theta)}\right) = \arctan\left(-\frac{1}{6} (3 \cos(2\theta) - 1) \csc(\theta) \sec(\theta)\right)
$$

### Plots of $\phi$ vs. $\theta$ and $$\| \vec{a} \|$$ vs. $\theta$

Here is the plot of $\phi$ against $\theta$:

![Angle of Total Acceleration vs. Angle Theta](/assets/img/pendulum_angle.png)

And here is the plot of the magnitude of the total acceleration:

![Magnitude of Total Acceleration vs. Angle Theta](/assets/img/pendulum_acceleration_magnitude.png)

### Tension Force

The tension force is calculated as:

$$
F_T = 3mg \sin(\theta)
$$

And here is the plot of the tension force:

![Tension Force vs. Angle Theta](/assets/img/pendulum_tension_force.png)

## Conclusion

This analysis reveals the following:
- As the angle $\theta$ increases, the total acceleration's direction shifts from pointing downward (at $\theta = 0^\circ$) to pointing upward (at $\theta = 90^\circ$), which aligns with the shift in the forces acting on the bob.
- The total acceleration magnitude increases from $g$ to $2g$ as $\theta$ changes from $0^\circ$ to $90^\circ$.
- The tension force also increases as the bob moves from the horizontal position to vertical, with a maximum at $\theta = 90^\circ$.

This experiment illustrates the effect of gravitational force and centripetal acceleration on a pendulum’s motion in low-gravity environments like the Moon.
