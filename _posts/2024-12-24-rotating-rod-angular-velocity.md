---
layout: post
title: "Comparing Angular Velocities for a Rotating Rod"
date: 2024-12-24
categories: [Rotational Dynamics, Physics]
tags: [angular velocity, conservation of angular momentum, rotation]
math: true
description: "Analyzing and comparing the final angular velocities of a rotating rod in three distinct cases using conservation of angular momentum."
---

## Problem Statement

Consider a rod of length $r$ and mass $M$. A particle of mass $m_p$ interacts with the rod in various scenarios. The goal is to determine and compare the final angular velocities of the rod ($\omega_{r,f}$) in three distinct cases, assuming conservation of angular momentum. The counterclockwise direction is defined as positive.

---

## Case 1: The Particle Rebounds Off the Rod

Using the conservation of angular momentum:

$$
L_i = L_f \Rightarrow L_{p,i} = L_{p,f} + L_{r,f}
$$

The angular momentum contributions are:

- Initial angular momentum of the particle: $L_{p,i} = r m_p v_p$
- Final angular momentum of the particle: $L_{p,f} = -r m_p v_{p,f}$ (negative since the particle rebounds)
- Final angular momentum of the rod: $L_{r,f} = \frac{1}{3} M r^2 \omega_{r,f}$

Substituting these into the conservation equation:

$$
r m_p v_p = -r m_p v_{p,f} + \frac{1}{3} M r^2 \omega_{r,f}
$$

Solving for $\omega_{r,f}$:

$$
\omega_{r,f} = \frac{3 (m_p v_{p,f} + m_p v_p)}{M r}
$$

---

## Case 2: The Particle Sticks to the Rod

Using the conservation of angular momentum:

$$
L_i = L_f \Rightarrow L_{p,i} = L_{p+r,f}
$$

The angular momentum contributions are:

- Initial angular momentum of the particle: $L_{p,i} = r m_p v_p$
- Final angular momentum of the combined system (particle + rod): 

$$
L_{p+r,f} = \left(\frac{1}{3} M r^2 + m_p r^2 \right) \omega_{r,f}
$$

Substituting into the conservation equation:

$$
r m_p v_p = \left(\frac{1}{3} M r^2 + m_p r^2 \right) \omega_{r,f}
$$

Solving for $\omega_{r,f}$:

$$
\omega_{r,f} = \frac{3 m_p v_p}{r (3 m_p + M)}
$$

---

## Case 3: The Particle Is Absorbed by the Rod (No Extra Mass)

Using the conservation of angular momentum:

$$
L_i = L_f \Rightarrow L_{p,i} = L_{r,f}
$$

The angular momentum contributions are:

- Initial angular momentum of the particle: $L_{p,i} = r m_p v_p$
- Final angular momentum of the rod: $L_{r,f} = \frac{1}{3} M r^2 \omega_{r,f}$

Substituting into the conservation equation:

$$
r m_p v_p = \frac{1}{3} M r^2 \omega_{r,f}
$$

Solving for $\omega_{r,f}$:

$$
\omega_{r,f} = \frac{3 m_p v_p}{M r}
$$

---

## Comparison of Angular Velocities

The angular velocities for the three cases are:

1. Case 1: $\omega_{r,f,1} = \frac{3 (m_p v_{p,f} + m_p v_p)}{M r}$
2. Case 2: $\omega_{r,f,2} = \frac{3 m_p v_p}{r (3 m_p + M)}$
3. Case 3: $\omega_{r,f,3} = \frac{3 m_p v_p}{M r}$

### Step 1: Comparing $\omega_{r,f,1}$ and $\omega_{r,f,3}$

From the expressions:

$$
\omega_{r,f,1} = \frac{3 m_p v_{p,f} + 3 m_p v_p}{M r} > \frac{3 m_p v_p}{M r} = \omega_{r,f,3}
$$

Thus:

$$
\omega_{r,f,1} > \omega_{r,f,3}
$$

### Step 2: Comparing $\omega_{r,f,3}$ and $\omega_{r,f,2}$

From the expressions:

$$
\omega_{r,f,3} = \frac{3 m_p v_p}{M r}
$$

and:

$$
\omega_{r,f,2} = \frac{3 m_p v_p}{r (3 m_p + M)}
$$

Since $M r > r (3 m_p + M)$:

$$
\omega_{r,f,3} > \omega_{r,f,2}
$$

---

## Final Order of Angular Velocities

Combining the results:

$$
\omega_{r,f,2} < \omega_{r,f,3} < \omega_{r,f,1}
$$

---

## Conclusion

This analysis demonstrates how different interactions between the particle and rod affect the final angular velocity of the rod. The results reflect the varying contributions of the particle's momentum and the distribution of mass in the system.
