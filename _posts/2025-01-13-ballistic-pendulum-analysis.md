---
layout: post
title: "Analyzing a Ballistic Pendulum: Conservation of Angular Momentum and Energy"
date: 2025-01-13
categories: [Classical Mechanics, Physics]
tags: [ballistic pendulum, angular momentum, conservation of energy]
math: true
description: "An in-depth analysis of a ballistic pendulum problem, demonstrating conservation of angular momentum and energy."
---

## Problem Statement

Imagine a ballistic pendulum system consisting of a plank of mass $M = 10 \, \text{kg}$ and length $L = 0.5 \, \text{m}$, which swings frictionlessly around a fixed axis $O$. A bullet of mass $m = 0.01 \, \text{kg}$ is fired at velocity $v_0$ directly into the center of the plank and becomes embedded in it. The plank and bullet system then swings to a maximum offset angle $\theta_{\text{max}} = 15^\circ$ from the vertical.

### Objectives:
1. Show that the system exhibits conservation of angular momentum during the collision.
2. Use conservation of mechanical energy to relate the angular velocity $\omega$ just after the collision to the maximum angle $\theta_{\text{max}}$.
3. Use conservation of angular momentum to determine the initial velocity $v_0$ of the bullet.

---

## Analysis

### (i) Conservation of Angular Momentum

To demonstrate that angular momentum is conserved during the collision, we must show that the net external torque $\tau_{\text{net}}$ acting on the system is zero. This ensures:

$$
\tau_{\text{net}} = \frac{\mathrm{d} L_{\text{net}}}{\mathrm{d}t} = 0 \quad \Rightarrow \quad L_{\text{net}} = \text{constant}.
$$

#### Torques Acting on the System:
- $\tau_{g,P}$: Torque due to gravity acting on the plank’s center of mass.
- $\tau_{g,B}$: Torque due to gravity acting on the bullet’s center of mass.
- $\tau_A$: Torque applied at the axis $O$.

The reference axis is chosen to be at $O$, so:
1. Both gravitational forces are parallel to their respective radial vectors, making $\tau_{g,P} = \tau_{g,B} = 0$.
2. The radial vector for $\tau_A$ has zero magnitude, so $\tau_A = 0$.

Thus:

$$
\tau_{\text{net}} = \tau_{g,P} + \tau_{g,B} + \tau_A = 0 \quad \Rightarrow \quad \frac{\mathrm{d} L_{\text{net}}}{\mathrm{d}t} = 0.
$$

This proves that angular momentum is conserved during the collision.

---

### (ii) Conservation of Mechanical Energy

After the collision, the system swings upward. The initial rotational kinetic energy is converted into gravitational potential energy at the maximum height. Using conservation of mechanical energy:

$$
K_i = U_f.
$$

#### Initial Kinetic Energy:
The rotational kinetic energy of the system just after the collision is:

$$
K_i = \frac{1}{2} I_{\text{total}} \omega^2,
$$

where $I_{\text{total}}$ is the total moment of inertia of the system about axis $O$:

$$
I_{\text{total}} = \frac{1}{3} M L^2 + m \left(\frac{L}{2}\right)^2.
$$

Substituting:

$$
K_i = \frac{1}{2} \left(\frac{1}{3} M L^2 + m \frac{L^2}{4}\right) \omega^2.
$$

#### Final Potential Energy:
At the maximum angle $\theta_{\text{max}}$, the center of mass of the system rises. The gravitational potential energy is:

$$
U_f = (M + m) g \Delta h,
$$

where $\Delta h$ is the vertical displacement of the center of mass:

$$
\Delta h = L \left(1 - \cos(\theta_{\text{max}})\right).
$$

Thus:

$$
U_f = (M + m) g L \left(1 - \cos(\theta_{\text{max}})\right).
$$

#### Relating $\omega$ to $\theta_{\text{max}}$:
Equating $K_i$ and $U_f$:

$$
\frac{1}{2} \left(\frac{1}{3} M L^2 + m \frac{L^2}{4}\right) \omega^2 = (M + m) g L \left(1 - \cos(\theta_{\text{max}})\right).
$$

Solve for $\omega$:

$$
\omega = \sqrt{\frac{2 g (M + m) (1 - \cos(\theta_{\text{max}}))}{L \left(\frac{1}{3} M + \frac{m}{4}\right)}}.
$$

---

### (iii) Conservation of Angular Momentum to Find $v_0$

During the collision, angular momentum is conserved:

$$
L_i = L_f.
$$

#### Initial Angular Momentum:
The bullet strikes the plank at a distance $\frac{L}{2}$ from the axis, so its initial angular momentum is:

$$
L_i = \left(\frac{L}{2}\right) m v_0.
$$

#### Final Angular Momentum:
The final angular momentum is due to the rotation of the combined system:

$$
L_f = I_{\text{total}} \omega,
$$

where:

$$
I_{\text{total}} = \frac{1}{3} M L^2 + m \frac{L^2}{4}.
$$

Equating $L_i$ and $L_f$:

$$
\left(\frac{L}{2}\right) m v_0 = \left(\frac{1}{3} M L^2 + m \frac{L^2}{4}\right) \omega.
$$

Solve for $v_0$:

$$
v_0 = \frac{\left(\frac{1}{3} M L^2 + m \frac{L^2}{4}\right) \omega}{\frac{L}{2} m}.
$$

Simplify:

$$
v_0 = \frac{2 L \left(\frac{1}{3} M + \frac{m}{4}\right) \omega}{m}.
$$

---

## Final Calculations

Substitute the given values ($M = 10 \, \text{kg}$, $m = 0.01 \, \text{kg}$, $L = 0.5 \, \text{m}$, $\theta_{\text{max}} = 15^\circ$, $g = 9.8 \, \text{m/s}^2$):

1. Compute $\omega$ using the expression from part (ii).
2. Use $\omega$ to find $v_0$ from part (iii).

### Result:
After substituting:

$$
\omega \approx 0.522 \, \text{rad/s}, \quad v_0 \approx 174.2 \, \text{m/s}.
$$

---

## Conclusion

This problem demonstrates the interplay between conservation of angular momentum and mechanical energy in a ballistic pendulum system. Through symbolic derivations, we rigorously related the maximum swing angle to the bullet's initial velocity.
