---
layout: post
title: "Physics of a Bicycle Jump: Flying Over a Container"
date: 2024-12-24
categories: [Classical Mechanics, Physics]
tags: [projectile motion, kinematics, angle of landing]
math: true
description: "Analyzing the physics behind a bicycle's jump over a container using kinematics and projectile motion."
---

## Problem Statement

Imagine a daredevil cyclist attempting to jump a container from the roof of a building. The building has a height of $H = 5.0 \, \text{m}$, and the container placed adjacent to the building has dimensions $h = 3.0 \, \text{m}$ (height) and $w = 4.5 \, \text{m}$ (width). The cyclist and bicycle are modeled as a point mass, and we want to answer the following questions:

1. What is the **minimum initial velocity** $v_0$ required for the cyclist to clear the container without hitting it?
2. If the cyclist jumps with the **minimum initial velocity**, what is the total **horizontal distance** $L$ they cover before landing back on the ground?
3. What is the **angle** $\alpha$ of the bicycle’s velocity with respect to the horizontal at the moment of landing?

---

## Assumptions and Setup

- The reference point (origin) is at the launch point.
- Positive $x$ points right (horizontal direction), and positive $y$ points downward (vertical direction).
- Gravity acts downward with acceleration $g = 10 \, \text{m/s}^2$.
- The trajectory of the bicycle follows the equations of projectile motion.

---

### (a) Minimum Initial Velocity $v_0$

The bicycle must fly over the container without hitting it. This means the trajectory of the bicycle must pass through the top-right corner of the container at point $(w, H-h)$, where $w = 4.5 \, \text{m}$ and $H - h = 2.0 \, \text{m}$.

#### Vertical Motion Equation:
The vertical position $y$ of the bicycle is given by:

$$
y = \frac{1}{2} g t^2
$$

#### Horizontal Motion Equation:
The horizontal position $x$ of the bicycle is given by:

$$
x = v_0 t \quad \Rightarrow \quad t = \frac{x}{v_0}
$$

Substituting $t = \frac{x}{v_0}$ into the vertical motion equation:

$$
y = \frac{1}{2} g \left(\frac{x}{v_0}\right)^2 \quad \Rightarrow \quad y = \frac{1}{2} \frac{g}{v_0^2} x^2
$$

At the point $(w, H-h)$:

$$
H - h = \frac{1}{2} \frac{g}{v_0^2} w^2
$$

Rearranging for $v_0$:

$$
v_0 = \sqrt{\frac{\frac{1}{2} g w^2}{H - h}}
$$

Substitute $g = 10 \, \text{m/s}^2$, $w = 4.5 \, \text{m}$, and $H - h = 2.0 \, \text{m}$:

$$
v_0 = \sqrt{\frac{\frac{1}{2} \cdot 10 \cdot 4.5^2}{2.0}} \approx 7.12 \, \text{m/s}
$$

The minimum initial velocity required is:

$$
v_0 \approx 7.12 \, \text{m/s}
$$

---

### (b) Total Horizontal Distance $L$

The total horizontal distance $L$ corresponds to the point where the cyclist lands back at the ground ($y = H$). From the vertical motion equation:

$$
y = \frac{1}{2} \frac{g}{v_0^2} x^2
$$

At the landing point $(L, H)$, substitute $y = H$:

$$
H = \frac{1}{2} \frac{g}{v_0^2} L^2 \quad \Rightarrow \quad L = \sqrt{\frac{2 H v_0^2}{g}}
$$

Substitute $v_0^2 = \frac{\frac{1}{2} g w^2}{H - h}$ from part (a):

$$
L = \sqrt{\frac{2 H \cdot \frac{\frac{1}{2} g w^2}{H - h}}{g}}
$$

Simplify:

$$
L = \sqrt{\frac{H w^2}{H - h}}
$$

Substitute $H = 5.0 \, \text{m}$, $w = 4.5 \, \text{m}$, and $H - h = 2.0 \, \text{m}$:

$$
L = \sqrt{\frac{5.0 \cdot 4.5^2}{2.0}} \approx 7.12 \, \text{m}
$$

The total horizontal distance is:

$$
L \approx 7.12 \, \text{m}
$$

---

### (c) Angle of Velocity $\alpha$ at Landing

At the landing point, the components of velocity are:

#### Horizontal Velocity:
The horizontal velocity remains constant throughout the motion:

$$
v_{f,x} = v_0
$$

#### Vertical Velocity:
From the vertical motion equation:

$$
v_{f,y} = g t
$$

At the landing point, $t = \frac{L}{v_0}$, so:

$$
v_{f,y} = g \frac{L}{v_0}
$$

The angle $\alpha$ of the velocity vector with respect to the horizontal is:

$$
\alpha = \arctan\left(\frac{v_{f,y}}{v_{f,x}}\right) = \arctan\left(\frac{g L}{v_0^2}\right)
$$

Substitute $v_0^2 = \frac{\frac{1}{2} g w^2}{H - h}$ and $L = \sqrt{\frac{H w^2}{H - h}}$:

$$
\alpha = \arctan\left(\frac{2 H}{\sqrt{\frac{H w^2}{H - h}}}\right)
$$

Simplify further and substitute values:

$$
\alpha = \arctan\left(\frac{2 \cdot 5.0}{\sqrt{\frac{5.0 \cdot 4.5^2}{2.0}}}\right) \approx 55^\circ
$$

The angle of velocity at landing is:

$$
\alpha \approx 55^\circ
$$

---

## Conclusion

The analysis reveals the following:

1. The minimum initial velocity required to clear the container is approximately $v_0 \approx 7.12 \, \text{m/s}$.
2. The total horizontal distance covered is $L \approx 7.12 \, \text{m}$.
3. The angle of velocity with the horizontal at landing is $\alpha \approx 55^\circ$.

This problem beautifully illustrates the principles of projectile motion and how physics governs the daring feats of cyclists and stunt performers!
