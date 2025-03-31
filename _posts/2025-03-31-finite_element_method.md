---
layout: post
title: "Finite Element Method"
date: 2025-03-31
categories: [Numerical Methods, Partial Differential Equations]
tags: [finite element method, weak formulation, shape functions, Poisson equation]
math: true
description: "A detailed exploration of the finite element method for the one-dimensional Poisson equation, including weak formulation, shape functions, and isoparametric mapping."
---

## Introduction

This post provides a detailed look at the **Finite Element Method (FEM)** for solving boundary value problems, focusing on the one-dimensional **Poisson equation**. We derive the **weak formulation**, discuss shape functions and their continuity properties, and explore how to assemble local contributions to form the global system of equations.

The main example is the Poisson equation
$$
u''(x) = f(x), \quad 0 \le x \le 1,
$$
subject to boundary conditions
$$
u(0) = 0 \quad \text{and} \quad u'(1) = 0.
$$

We assume a constant right-hand side $f(x) = \overline{f}$ for simplicity, so the exact solution is
$$
u(x) = \tfrac{1}{2}\,\overline{f}\, x^2 \;-\; \overline{f}\, x.
$$

---

## 1. The Strong Form and the Weak Form

### 1.1 Strong Form

The **strong form** of our boundary value problem (BVP) states:
$$
\begin{cases}
u''(x) = f(x), & 0 \le x \le 1,\\
u(0) = 0,\\
u'(1) = 0.
\end{cases}
$$

This is called “strong” because it assumes $u(x)$ is at least twice differentiable everywhere on $[0,1]$, allowing $u''(x)$ to make sense pointwise.

### 1.2 Weak Formulation

To derive the **weak form**, we multiply both sides of $u''(x) = f(x)$ by a **test function** $v(x)$ that satisfies the appropriate boundary conditions (for instance, $v(0) = 0$ since $u(0) = 0$ is an essential boundary condition). Then we integrate over $[0,1]$:
$$
\int_{0}^{1} u''(x)\, v(x)\, dx \;=\; \int_{0}^{1} f(x)\, v(x)\, dx.
$$

Next, we apply **integration by parts**:
$$
\int_{0}^{1} u''(x)\, v(x)\, dx 
=\, u'(1)\,v(1) \;-\; u'(0)\,v(0)
\;-\; \int_{0}^{1} u'(x)\, v'(x)\, dx.
$$

Given the boundary condition $u'(1) = 0$, and choosing $v(0)=0$ to match $u(0)=0$, the boundary term vanishes:
$$
u'(1)\,v(1) \;-\; u'(0)\,v(0) = 0.
$$

Hence, the weak form becomes:
$$
-\int_{0}^{1} u'(x)\,v'(x)\, dx \;=\; \int_{0}^{1} f(x)\,v(x)\, dx.
$$
Or equivalently,
$$
\int_{0}^{1} u'(x)\,v'(x)\, dx 
\;=\; -\int_{0}^{1} f(x)\,v(x)\, dx.
$$

**Key insight**: In the weak form, we only require $u$ and $v$ to be once differentiable (instead of twice). This relaxation allows solutions that might not satisfy the strong form pointwise, but still satisfy the integrated (weak) form. This is precisely why the weak form is better suited for **finite element** discretizations.

---

## 2. The Finite Element Method

### 2.1 Discretization of the Domain

We partition the interval $[0,1]$ into smaller “elements.” For example, dividing $[0,1]$ into 5 subintervals might yield node points
$$
x_0 = 0,\quad x_1 = 0.2,\quad x_2 = 0.4,\quad x_3 = 0.6,\quad x_4 = 0.8,\quad x_5 = 1.0.
$$
At each node, we store an unknown value $u_i = u(x_i)$. Between nodes, we **approximate** $u(x)$ using **shape functions** $\{N_i(x)\}$.

### 2.2 Shape Functions

A typical piecewise linear approximation in 1D uses **triangular** (or linear) shape functions:
$$
u(x) \;=\; \sum_{i=0}^{5} u_i \, N_i(x).
$$
Each shape function $N_i(x)$ is “hat”-shaped: it is 1 at node $x_i$ and 0 at all other nodes. For instance, near $x_1=0.2$:
$$
N_1(x) = 
\begin{cases}
5x, & 0 \le x < 0.2,\\
2 - 5x, & 0.2 \le x < 0.4,\\
0, & \text{elsewhere}.
\end{cases}
$$
Linear elements imply that $u'(x)$ is piecewise constant and may not be continuous at the element boundaries.

---

### 2.3 Discrete Weak Form

We substitute the finite element approximation 
$$
u(x)= \sum_{i} u_i\, N_i(x),
\quad
v(x)= \sum_{j} v_j\, N_j(x)
$$
into the weak form:
$$
\int_0^1 u'(x)\,v'(x)\,dx 
= 
-\int_0^1 f(x)\,v(x)\,dx.
$$

In index notation, let:
$$
u'(x) = \sum_{i} u_i \, N_i'(x),
\quad
v'(x) = \sum_{j} v_j \, N_j'(x).
$$
Then,
$$
\int_0^1 
\Bigl(\sum_{i} u_i \, N_i'(x)\Bigr)
\Bigl(\sum_{j} v_j \, N_j'(x)\Bigr)\,dx 
\;=\; 
-\int_0^1 f(x)\,\Bigl(\sum_{k} v_k \,N_k(x)\Bigr)\,dx.
$$

Rearranging sums and integrals, we identify:
$$
\underbrace{
\int_0^1 
N_i'(x)\,N_j'(x)\,dx
}_{K_{ij}}
\quad\text{and}\quad
\underbrace{
-\int_0^1 
f(x)\,N_k(x)\,dx
}_{F_{k}},
$$
leading to a **global system**:
$$
K\,U = F,
$$
where $U$ is the vector of unknown coefficients $\bigl(u_0,u_1,\dots,u_5\bigr)$, $K$ is the **stiffness matrix**, and $F$ is the **load vector**.

- **Stiffness matrix**: $K_{ij} = \int_0^1 N_i'(x)\,N_j'(x)\,dx.$  
- **Load vector**: $F_i = -\int_0^1 f(x)\,N_i(x)\,dx.$

---

## 3. Assembling Element Matrices

### 3.1 Elemental Shape Functions

In practice, we subdivide $[0,1]$ into elements, and each element $e$ contributes a local stiffness matrix $K^e$ and a local load vector $F^e$. For an element $[x_{e},x_{e+1}]$, we define local shape functions $\{N_0^e(x), N_1^e(x)\}$, each supported only on that element. For linear 1D elements:

- $N_0^e(x)$ is 1 at $x_e$ and 0 at $x_{e+1}$,
- $N_1^e(x)$ is 0 at $x_e$ and 1 at $x_{e+1}$.

Then the **element stiffness** is:
$$
K^e_{ij} 
= \int_{x_e}^{x_{e+1}}
\frac{\partial N_i^e(x)}{\partial x}\,
\frac{\partial N_j^e(x)}{\partial x}\, dx, 
\quad i,j=0,1.
$$
The **element load** is:
$$
F^e_{i} 
= -\int_{x_e}^{x_{e+1}} 
f(x)\, N_i^e(x)\, dx,
\quad i=0,1.
$$

### 3.2 Reference Element and Isoparametric Mapping

To simplify integration, we often map each element $[x_e, x_{e+1}]$ onto a **reference interval** $[-1,1]$. The linear mapping $\phi_e(\xi)$ can be written as:
$$
x = \phi_e(\xi) 
= \frac{x_e + x_{e+1}}{2} \;+\; \frac{x_{e+1}-x_e}{2}\,\xi,
\quad -1 \le \xi \le 1.
$$
Correspondingly,
$$
\frac{dx}{d\xi} = \frac{x_{e+1}-x_e}{2}.
$$
We define **reference shape functions** $\mathcal{N}_0(\xi)$ and $\mathcal{N}_1(\xi)$ on $[-1,1]$:
$$
\mathcal{N}_0(\xi) = \tfrac{1}{2}\bigl(1 - \xi\bigr), 
\quad
\mathcal{N}_1(\xi) = \tfrac{1}{2}\bigl(1 + \xi\bigr),
$$
and use these to assemble $K^e, F^e$ by integrating with respect to $\xi$. We often do this numerically with **Gaussian quadrature**.

---

## 4. Example: Constructing the Global System

After computing each element’s local matrices $(K^e,F^e)$, we “assemble” them into global matrices $(K,F)$. This process adds the entries of $K^e$ and $F^e$ to the appropriate global rows and columns corresponding to each element’s global node indices. The final system has the form
$$
K\, U = F,
$$
where $U$ includes all unknown nodal values $\{u_i\}$. We then apply boundary conditions, e.g. $u_0=0$, $u'(1)=0$ (the latter modifies the system suitably or sets constraints on the degrees of freedom). Solving the resulting linear system yields the finite element approximation $\{u_i\}$.

---

## 5. Observations and Concluding Remarks

1. **Sparse and Symmetric**: The stiffness matrix $K$ in 1D Poisson problems is symmetric and banded. For linear elements on a uniform mesh, it is tridiagonal (except for modifications due to boundary conditions). This sparsity is crucial for efficient solvers.
2. **Approximation Quality**: Linear elements yield piecewise-linear solutions. As the mesh is refined (more, smaller elements), the finite element solution converges to the true solution of the Poisson equation.
3. **Extension to Higher Dimensions**: The same principles apply in 2D/3D, where elements can be triangles or tetrahedra, and shape functions must satisfy appropriate continuity requirements. The mathematics of the **weak form**, the concept of local shape functions, assembly of element matrices, and boundary conditions remain the same.

---

## Conclusion

The finite element method transforms a **strong-form** differential equation into a **weak formulation**, which allows the use of piecewise polynomial approximations and test functions. By discretizing the domain into elements, defining shape functions, and assembling local contributions, we obtain a global linear system to solve for nodal values. This example in 1D demonstrates the essential theory and steps; higher-dimensional problems follow a similar structure, with more complex shape functions and integrals.

