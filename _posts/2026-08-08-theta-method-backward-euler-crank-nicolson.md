---
layout: post
title: "The θ-Method: Backward Euler and Crank–Nicolson"
date: 2026-08-08
categories: [Numerical Methods, Partial Differential Equations]
tags: [theta method, backward Euler, Crank-Nicolson, finite differences, parabolic PDE, stability]
math: true
description: "A unified derivation of the θ-method for time discretization, specializing to Forward Euler, Backward Euler, and Crank–Nicolson, with truncation error, A-/L-stability, and the heat-equation amplification factors."
---

## Introduction

When solving parabolic PDEs such as the heat equation, the choice of **time integrator** controls accuracy, stability, and whether high-frequency modes are damped or ring. Three classical one-step schemes—**Forward Euler**, **Backward Euler**, and **Crank–Nicolson**—are special cases of a single family called the **θ-method** (or θ-rule).

This post derives that family, fixes a consistent convention for $\theta$, works out truncation error and stability, and applies the scheme to the one-dimensional heat equation. The goal is numerical-analysis intuition, not a research dump: these are the same discrete residuals that appear later in finite-difference baselines and in numerics-informed neural solvers.

---

## 1. Convention for $\theta$

There are two common conventions for $\theta$ in the literature. **This post uses the PDE / scientific-computing convention** (Langtangen, Süli, Higham, and most SciML notes):

$$
\frac{u^{n+1}-u^{n}}{\Delta t}
=
\theta\, f\bigl(t_{n+1},u^{n+1}\bigr)
+(1-\theta)\, f\bigl(t_{n},u^{n}\bigr),
\qquad \theta\in[0,1].
$$

Under this definition:

| $\theta$ | Method | Type |
|:---:|:---|:---|
| $0$ | Forward Euler | explicit |
| $1/2$ | Crank–Nicolson (trapezoidal rule) | implicit |
| $1$ | Backward Euler (implicit Euler) | implicit |

**Warning.** Some lecture notes (e.g. Cambridge DAMTP) *flip* the weights, so that $\theta=1$ is Forward Euler. Always check which weight multiplies $f^{n+1}$ before comparing formulas.

For a linear ODE $u'=Au$, the update is

$$
\bigl(I-\Delta t\,\theta A\bigr)\,u^{n+1}
=
\bigl(I+\Delta t\,(1-\theta)A\bigr)\,u^{n}.
$$

---

## 2. Derivation from Quadrature

Integrate $u'=f(t,u)$ from $t_n$ to $t_{n+1}=t_n+\Delta t$:

$$
u(t_{n+1})-u(t_n)
=
\int_{t_n}^{t_{n+1}} f\bigl(t,u(t)\bigr)\,dt.
$$

Approximate the integral by a convex combination of the endpoint values:

- left rectangle $\Rightarrow$ Forward Euler,
- right rectangle $\Rightarrow$ Backward Euler,
- trapezoid $\Rightarrow$ Crank–Nicolson.

The $\theta$-rule is exactly that one-parameter family of rectangle/trapezoid rules. For nonlinear $f$ and $\theta\neq 0$, each step requires solving an (in general nonlinear) algebraic equation for $u^{n+1}$.

**Historical note.** Crank–Nicolson for the heat equation goes back to J. Crank and P. Nicolson, *Proc. Cambridge Philos. Soc.* **43** (1947), 50–67. Spelling is **Nicolson** (one $h$).

---

## 3. Truncation Error and Order

Insert the exact solution into the $\theta$-scheme and Taylor-expand. The leading local error term is proportional to

$$
\Bigl(\tfrac12-\theta\Bigr)\Delta t\, u''(t_n)
$$

(up to how the residual is normalized). Consequently:

- if $\theta\neq\tfrac12$, the method is **first-order** accurate in time (global error $O(\Delta t)$);
- if $\theta=\tfrac12$, that term cancels and the method is **second-order** (global error $O(\Delta t^{2})$ for smooth data).

With a standard centered second-difference Laplacian, space is typically $O(\Delta x^{2})$. So on the heat equation one often quotes:

- Backward Euler: $O(\Delta t+\Delta x^{2})$,
- Crank–Nicolson: $O(\Delta t^{2}+\Delta x^{2})$.

---

## 4. Absolute Stability: $R(z)$, A-Stability, L-Stability

Apply the method to the Dahlquist test equation $u'=\lambda u$ and set $z=\Delta t\,\lambda$. The numerical update is $u^{n+1}=R(z)\,u^{n}$ with **stability function**

$$
R(z)
=
\frac{1+(1-\theta)z}{1-\theta z}.
$$

Definitions:

- **A-stable**: the stability region $\{z:|R(z)|\le 1\}$ contains the closed left half-plane $\operatorname{Re}(z)\le 0$.
- **L-stable**: A-stable and $\displaystyle\lim_{z\to\infty}R(z)=0$.

For the $\theta$-method,

$$
\lim_{z\to\infty} R(z)=\frac{1-\theta}{\theta}.
$$

Hence:

- $\theta\ge\tfrac12$ is **A-stable**,
- only $\theta=1$ (Backward Euler) is **L-stable**.

Crank–Nicolson ($\theta=\tfrac12$) is A-stable but not L-stable: $|R(\infty)|=1$. That fact drives the oscillation discussion below.

---

## 5. Application: 1D Heat Equation

Consider

$$
u_t=\alpha\, u_{xx},
\qquad \alpha>0.
$$

Discretize space with the usual three-point stencil and time with the $\theta$-rule:

$$
\frac{u_i^{n+1}-u_i^{n}}{\Delta t}
=
\alpha\Biggl[
\theta\frac{u_{i+1}^{n+1}-2u_i^{n+1}+u_{i-1}^{n+1}}{\Delta x^{2}}
+(1-\theta)\frac{u_{i+1}^{n}-2u_i^{n}+u_{i-1}^{n}}{\Delta x^{2}}
\Biggr].
$$

Introduce the **Fourier number** $F=\alpha\Delta t/\Delta x^{2}$. For $\theta\neq 0$ each step is a tridiagonal linear solve in 1D.

### 5.1 Crank–Nicolson form

With $\theta=\tfrac12$ and $r=\alpha\Delta t\big/(2\Delta x^{2})$,

$$
-r\,u_{i+1}^{n+1}+(1+2r)\,u_i^{n+1}-r\,u_{i-1}^{n+1}
=
r\,u_{i+1}^{n}+(1-2r)\,u_i^{n}+r\,u_{i-1}^{n}.
$$

Equivalently, CN is the average of Forward Euler and Backward Euler residuals at the two time levels (not merely “averaging two solvers”).

### 5.2 Von Neumann amplification factors

Seek modal solutions $u_i^{n}=A^{n}e^{\mathrm{i}k i\Delta x}$. Writing $p=\tfrac12 k\Delta x$, the classical amplification factors are:

| Scheme | Amplification factor $A$ |
|:---|:---|
| Forward Euler | $1-4F\sin^{2}p$ |
| Backward Euler | $\bigl(1+4F\sin^{2}p\bigr)^{-1}$ |
| Crank–Nicolson | $\dfrac{1-2F\sin^{2}p}{1+2F\sin^{2}p}$ |

The exact modal factor is $A_{\mathrm{ex}}=e^{-\alpha k^{2}\Delta t}=e^{-4F p^{2}}$ (with $p=\tfrac12 k\Delta x$).

For the linear heat equation:

- $\theta\ge\tfrac12$ is **unconditionally stable** in the von Neumann sense ($|A|\le 1$ for all $\Delta t>0$);
- $\theta<\tfrac12$ is only **conditionally** stable (Forward Euler needs a CFL-type restriction, classically $F\le\tfrac12$).

---

## 6. Crank–Nicolson Oscillations

Unconditional stability does **not** mean every scheme behaves well for large $\Delta t$.

For Crank–Nicolson, high-frequency modes have $A\approx -1$ when $F$ is large. Those components flip sign each step and are only weakly damped. The effect is visible for discontinuous or rough initial data, or when the initial condition is inconsistent with the boundary data.

Backward Euler strongly damps stiff modes (L-stability): $A\to 0$ as $F\to\infty$. That is why BE is often preferred for stiff transients or discontinuous data, despite being only first-order.

Common remedies for CN ringing include:

1. take one or two Backward Euler steps, then switch to CN (**Rannacher smoothing**)—overall second-order accuracy can be retained if done carefully;
2. use $\theta$ slightly larger than $1/2$ (e.g. $0.55$) to buy damping at the cost of formal order;
3. refine $\Delta t$ until high modes are adequately resolved.

---

## 7. Comparison Summary

| Property | Forward Euler | Crank–Nicolson | Backward Euler |
|:---|:---:|:---:|:---:|
| $\theta$ | $0$ | $1/2$ | $1$ |
| Temporal order | $1$ | $2$ | $1$ |
| Heat-equation von Neumann | conditional | unconditional | unconditional |
| A-stable | no | yes | yes |
| L-stable | no | no | yes |
| High-mode damping | weak / unstable if $F$ large | weak ($A\approx-1$) | strong |
| Linear algebra / step | explicit | tridiagonal solve | tridiagonal solve |

**Rule of thumb.** Prefer Crank–Nicolson for smooth solutions when you want second-order time accuracy and moderate steps. Prefer Backward Euler when robustness and damping matter more than formal order—stiff problems, discontinuous data, or large steps.

---

## 8. Bridge to Discrete SciML Residuals

In classical FD codes, one *solves* the $\theta$-scheme for $u^{n+1}$. In residual-based neural PDE solvers, one instead *minimizes* a discrete residual built from the same stencil. For example, a Backward Euler residual on a grid looks like

$$
r^{n+1}
=
\hat u^{n+1}-\hat u^{n}
-\Delta t\, f^{n+1}
-\Delta t\,\Delta_h \hat u^{n+1},
$$

and Crank–Nicolson replaces the right-hand side by the $\theta=\tfrac12$ average. Numerics-informed neural networks (NINNs), introduced by Celaya, Kirk, Fuentes, and Riviere (2024), fix a finite-difference operator and train against such residuals; the $\theta$-method is the classical time discretization underneath NINN-BE and NINN-CN. The neural architecture is a separate story—this post is only about the time discretization.

---

## Conclusion

The $\theta$-method packages Forward Euler, Backward Euler, and Crank–Nicolson into one formula. Lock the convention ($\theta$ weights the *new* time level), read off order from whether $\theta=\tfrac12$, and separate **stability** ($|A|\le 1$) from **damping** (L-stability). For the heat equation, CN is second-order and unconditionally stable but can oscillate; BE is first-order, unconditionally stable, and strongly damping. That trade-off is the core numerical idea behind choosing a time integrator for parabolic problems—and behind writing consistent discrete residuals for SciML solvers.

---

## Further Reading

1. H. P. Langtangen — finite-difference schemes for diffusion / the $\theta$-rule ([notes](https://hplgit.github.io/num-methods-for-PDEs/doc/pub/diffu/html/slides_diffu-1.html)).
2. CU Numerical Computation — $R(z)$, A-stability, L-stability ([notes](https://cu-numcomp.github.io/spring22/slides/2022-04-22-adaptivity.html)).
3. J. Crank and P. Nicolson, *A practical method for numerical evaluation of solutions of partial differential equations of the heat-conduction type*, Proc. Cambridge Philos. Soc. **43** (1947), 50–67 ([DOI](https://doi.org/10.1017/S0305004100023197)).
4. A. Celaya, K. Kirk, D. Fuentes, and B. Riviere, *Solutions to elliptic and parabolic problems via finite difference based unsupervised small linear convolutional neural networks*, Comput. Math. Appl. **174** (2024), 31–42 ([DOI](https://doi.org/10.1016/j.camwa.2024.08.013); [arXiv:2311.00259](https://arxiv.org/abs/2311.00259)).
