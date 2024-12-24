---
layout: post
title: "Comparing Moments of Inertia for Disk Segments"
date: 2024-12-24
categories: [Rotational Dynamics, Physics]
tags: [moment of inertia, symmetry, solid disk]
math: true
description: "Analyzing the moments of inertia for various fractions of solid disks with different masses and radii."
---

## Problem Statement

The moment of inertia for a solid disk about an axis passing through its center and perpendicular to the plane of the disk is given by:

$$
I = \frac{1}{2} M R^2
$$

where $M$ is the mass of the disk and $R$ is the radius of the disk.

We are tasked with comparing the moments of inertia of four shapes derived from disks with the following properties:

- Shape A: Half of a disk, with total mass $M$ and radius $R$.
- Shape B: A quarter of a disk, with total mass $M$ and radius $R$.
- Shape C: A quarter of a disk, with total mass $2M$ and radius $R$.
- Shape D: A quarter of a disk, with total mass $M$ and radius $2R$.

Assume uniform density across all shapes. By symmetry, the moment of inertia for each shape can be calculated based on its fraction of a full disk.

---

## Analysis of Each Shape

### Shape A: Half of a Disk

For Shape A, the disk is split into two equal halves. The moment of inertia for half a disk is:

$$
I_A = \frac{1}{2} \left(\frac{1}{2} (2M) R^2\right)
$$

Simplifying:

$$
I_A = \frac{1}{2} M R^2
$$

---

### Shape B: A Quarter of a Disk

For Shape B, the disk is split into four equal quarters. The moment of inertia for a quarter of a disk is:

$$
I_B = \frac{1}{4} \left(\frac{1}{2} (4M) R^2\right)
$$

Simplifying:

$$
I_B = \frac{1}{2} M R^2
$$

---

### Shape C: A Quarter of a Disk with Double Mass

For Shape C, the disk is split into four equal quarters, but the total mass of the disk is $2M$. The moment of inertia for a quarter of this disk is:

$$
I_C = \frac{1}{4} \left(\frac{1}{2} (8M) R^2\right)
$$

Simplifying:

$$
I_C = M R^2
$$

---

### Shape D: A Quarter of a Disk with Double Radius

For Shape D, the disk is split into four equal quarters, but the radius of the disk is $2R$. The moment of inertia for a quarter of this disk is:

$$
I_D = \frac{1}{4} \left(\frac{1}{2} (4M) (2R)^2\right)
$$

Simplifying:

$$
I_D = 2 M R^2
$$

---

## Comparison of Moments of Inertia

From the above calculations:

- Shape A: $I_A = \frac{1}{2} M R^2$
- Shape B: $I_B = \frac{1}{2} M R^2$
- Shape C: $I_C = M R^2$
- Shape D: $I_D = 2 M R^2$

Thus, the moments of inertia are ordered as follows:

$$
I_A = I_B < I_C < I_D
$$

---

## Conclusion

The comparison shows how the mass and radius of a disk segment influence its moment of inertia. Larger radii and higher mass proportions significantly increase the moment of inertia due to their squared dependence in the formula $I = \frac{1}{2} M R^2$.
