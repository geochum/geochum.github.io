---
layout: post
title: "Physics of a Fly-Board: Lifting a Rider and Calculating Pump Power"
date: 2025-01-20
categories: [Fluid Mechanics, Physics]
tags: [fluid dynamics, thrust, power, fly-board]
math: true
description: "Analyzing the physics of a fly-board by calculating the thrust required to lift the rider and the power needed for steady flow."
---

## Problem Statement

A **fly-board** is a device that uses high-velocity water to produce thrust, allowing a rider to hover above the ground. The device consists of:

- A small platform (the board) connected by a thick hose to a powerful water pump.
- Water is forced up the hose and exits downward through nozzles, generating thrust that lifts the rider.

We make the following assumptions:

- The total mass of the rider, board, and hose portion is $M = 100\,\text{kg}$.
- Water is treated as an ideal fluid with density $\rho = 1000\,\text{kg/m}^3$.
- The hose is vertical with an inner diameter $d = 0.11\,\text{m}$, so $r = \frac{d}{2} = 0.055\,\text{m}$.
- Water enters and exits the board at the same speed $v$, with the flow reversed by $180^\circ$ inside the board.
- The acceleration of gravity is $g = 9.81\,\text{m/s}^2$.

### Tasks

1. **(a)** Determine the velocity $v$ of water needed to lift the rider in steady hover.  
2. **(b)** Calculate the minimum power $P$ required for the pump to sustain steady flow when the rider is hovering at a height $h = 7.0\,\text{m}$ above the pump's water inlet.

---

## Solution

### (a) Velocity of Water for Steady Hover

We want to find the flow speed $v$ that provides enough thrust to balance the weight $Mg$ of the rider and board.

#### 1. Mass Flow Rate

Let $\dot{m}$ be the mass flow rate of water through the hose:

$$
\frac{dm}{dt} 
= \rho \, A \, v 
= \rho \,\pi\,r^2\,v,
$$

where $A = \pi r^2$ is the hose cross-sectional area.

#### 2. Force on the Water (Momentum Change)

Within the board, water velocity is reversed from upward ($+v$) to downward ($-v$). Thus, the net velocity change per unit mass is

$$
\Delta v 
= v_{\text{out}} - v_{\text{in}}
= (-v) - (+v)
= -\,2v.
$$

The rate of change of the water’s momentum (force on the water by the board) is

$$
F_{w,M}
= \frac{dm}{dt} \,\Delta v
= (\rho \,\pi\,r^2\,v)\,(-2v)
= -\,2\,\pi\,\rho\,r^2\,v^2.
$$

By **Newton’s 3rd Law**, the force on the **rider+board** from the water is the opposite:

$$
F_{M,w}
= -\,F_{w,M}
= 2\,\pi\,\rho\,r^2\,v^2.
$$

#### 3. Force Balance for Hover

To hover, the upward thrust $F_{M,w}$ must equal the weight $Mg$:

$$
F_{M,w} 
= M\,g
\quad \Longrightarrow \quad
2\,\pi\,\rho\,r^2\,v^2 
= M\,g.
$$

Solving for $v$:

$$
v 
= \sqrt{\frac{M\,g}{2\,\pi\,\rho\,r^2}}.
$$

---

### (b) Minimum Pump Power

We now compute the power $P$ that the pump must deliver to keep the rider at height $h$ above the inlet.

#### 1. Energy per Unit Mass

Each kilogram of water gains:

- Gravitational potential energy $g\,h$,
- Kinetic energy $\tfrac12\,v^2$.

Hence, **per unit mass** of water, the energy is

$$
g\,h 
+ \frac12\,v^2.
$$

#### 2. Power = Energy per Time

The pump supplies this energy to a mass flow rate $\dot{m}$:

$$
P_{\text{pump}}
= \dot{m}
\Bigl(
  g\,h 
  + \tfrac12\,v^2
\Bigr)
= \rho\,\pi\,r^2\,v
\Bigl(
  g\,h 
  + \tfrac12\,v^2
\Bigr).
$$

In expanded form, you might also see:

$$
P_{\text{pump}}
= \frac12\,\pi\,\rho\,r^2\,v
\Bigl(
  2\,g\,h 
  + v^2
\Bigr).
$$

---

## Final Calculations

Plug in the known values:

- $M = 100\,\text{kg}$
- $\rho = 1000\,\text{kg/m}^3$
- $r = 0.055\,\text{m}$
- $g = 9.81\,\text{m/s}^2$
- $h = 7.0\,\text{m}$

1. **Water speed $v$:**

$$
v 
= \sqrt{
  \frac{(100)\cdot(9.81)}
       {2\,\pi\,(1000)\,(0.055)^2}
}
\approx
\sqrt{51.6}
\approx
7.2\,\text{m/s}.
$$

2. **Pump Power $P_{\text{pump}}$:**

First, note:

$$
v^2 \approx (7.2)^2 \approx 51.8,
\quad
2\,g\,h
= 2 \times 9.81 \times 7.0
\approx 137.3.
$$

Then:

$$
\dot{m}
= \rho\,\pi\,r^2\,v
\approx 1000\,\pi\,(0.055)^2 \times 7.2
\approx 68\,\text{kg/s}.
$$

So,

$$
P_{\text{pump}}
= \dot{m}
\Bigl(g\,h + \tfrac12\,v^2\Bigr)
\approx
68
\Bigl(9.81 \times 7.0 + \tfrac12 \times 51.8\Bigr).
$$

Inside the parentheses:

$$
g\,h = 9.81 \times 7.0 = 68.7,
\quad
\tfrac12\,v^2 = 25.9,
\quad
\text{sum} = 68.7 + 25.9 = 94.6.
$$

Hence,

$$
P_{\text{pump}}
\approx
68 \times 94.6
\approx
6430\,\text{J/s}
= 6.43\,\text{kW}.
$$

Rounding slightly, we get about $6.4\text{–}6.5\,\text{kW}$.

---

## Final Results

1. **Velocity of Water**:

$$
v \approx 7.2\,\text{m/s}.
$$

2. **Minimum Pump Power**:

$$
P_{\text{pump}}
\approx
6.4\text{–}6.5\,\text{kW}.
$$

---

### Conclusion

By reversing the water flow from upward to downward at about $7.2\,\text{m/s}$, the fly-board produces enough thrust to lift a $100\,\text{kg}$ rider and board. In an ideal frictionless scenario, maintaining that flow at $7\,\text{m}$ height requires about $6.4\,\text{kW}$ of pump power. Real systems will require more power to account for losses, but this analysis highlights the fundamental physics of momentum change and energy demands in a fly-board system.
