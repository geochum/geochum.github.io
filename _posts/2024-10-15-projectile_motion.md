---
layout: post
title: Projectile Motion with the Same Maximum Height
date: 2024-10-15
categories: [Classical Mechanics]
tags: [projectiles, kinematics, time-of-flight]
math: true
description: "Explore how projectiles with varying speeds and angles can achieve the same maximum height and flight time. We demonstrate that the flight time remains constant regardless of initial speed."
---


## Introduction

Imagine launching different projectiles with varying initial speeds and angles, all aimed to reach the same maximum height. How can we determine if the time of flight will be the same for each? Here's an interesting approach to solving this problem.

## Derivation

We'll show that the time of flight is the same regardless of their initial velocities.

First, the total time of flight $ t_{\text{flight}} $ for any projectile can be expressed as:

$$
t_{\text{flight}} = \frac{2v_0 \sin \theta}{g}
$$

Let the initial velocity be $ v_0 $, and the angle of projection be $ \theta $. The vertical component of the initial velocity is given by:

$$
v_{0y} = v_0 \sin \theta
$$

The maximum height $ h_{\text{max}} $ is reached when the vertical velocity becomes zero. Using the kinematic equation for vertical motion:

$$
v_y^2 = v_{0y}^2 - 2gh_{\text{max}}
$$

Setting $ v_y = 0 $ at the maximum height, we have:

$$
0 = v_0^2 \sin^2 \theta - 2gh_{\text{max}}
$$

Solving for $ h_{\text{max}} $, we get:

$$
h_{\text{max}} = \frac{v_0^2 \sin^2 \theta}{2g}
$$

Since the problem states that all projectiles reach the same maximum height, we can equate $ h_{\text{max}} $ for any two projectiles with different initial velocities:

$$
\frac{v_0^2 \sin^2 \theta}{2g} = \frac{v_0'^2 \sin^2 \theta'}{2g}
$$

Canceling out the common terms and simplifying:

$$
v_0 \sin \theta = v_0' \sin \theta'
$$

This shows that the vertical components of the initial velocities must be the same for all projectiles.

Now, the total time of flight $ t_{\text{flight}} $ for any projectile is given by:

$$
t_{\text{flight}} = \frac{2v_{0y}}{g} = \frac{2v_0 \sin \theta}{g}
$$

Since $ v_0 \sin \theta = v_0' \sin \theta' $, the time of flight is the same for all projectiles.
