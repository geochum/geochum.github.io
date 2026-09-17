---
layout: default
icon: fas fa-flask
order: 2
title: Research
---

# Research

Classical time-stepping for parabolic PDEs is stable, but it becomes expensive on fine grids. Networks trained only on a residual in the continuum — **physics-informed neural networks (PINNs)** — often struggle with discrete structure and boundary conditions. I work on **numerics-informed** solvers: the network is trained on a **discrete residual** of a chosen scheme (in the thesis, Backward Euler with a five-point Laplacian), with exact Dirichlet conditions enforced by **boundary lifting**. At Sandia I reused those pretrained local solvers as subdomain problems inside **overlapping Schwarz** domain decomposition.

Selected talks are listed on the [About](/about/) page.

## Numerics-Informed Neural Networks for parabolic PDEs (Rice)

Under the direction of **Dr. Beatrice Riviere**, I extend **Numerics-Informed Neural Networks (NINNs)** for two-dimensional parabolic problems, including the heat equation. NINNs were introduced by [Celaya, Kirk, Fuentes, and Riviere (2024)](https://doi.org/10.1016/j.camwa.2024.08.013) ([arXiv:2311.00259](https://arxiv.org/abs/2311.00259); code [aecelaya/pde-nets](https://github.com/aecelaya/pde-nets)) as unsupervised, finite-difference–based convolutional solvers.

**Method.** A compact U-Net is trained on the discrete residual of Backward Euler plus a five-point Laplacian. Dirichlet data enter through boundary lifting rather than penalty terms. I compare this solver to PINNs and to the **same** finite-difference scheme; those PINN baselines are part of the Rice thesis, not the Sandia internship.

**What I did.** I implemented the PyTorch training pipelines, ran GPU experiments on Rice **NOTS**, and analyzed manufactured-solution error, stability, and convergence across training schedules. On selected smooth problems the NINN shows at least second-order convergence and smaller error than the same finite-difference scheme.

**Links and writing.** Code: [geochum/neural-pde-solvers](https://github.com/geochum/neural-pde-solvers). I documented the study in an M.A. thesis (defended 9 December 2025; conferred 9 May 2026). A journal manuscript with Adrian Celaya and Beatrice Riviere is in preparation (working title below).

## Hybrid NINN–FOM overlapping Schwarz (Sandia CSRI, Summer 2026)

**Overlapping Schwarz** iterates on overlapping subdomains coupled through interface data. Mentored by **Dr. Irina Tezaur**, I built [pde-solver-lab](https://github.com/geochum/pde-solver-lab) for two-dimensional **advection–diffusion**. Each subdomain can be a classical finite-difference full-order model (FOM) or a NINN; the subdomains are coupled through interface data. I trained NINNs offline on discrete residual losses with exact Dirichlet conditions and reused them as local solvers instead of retraining every Schwarz iteration, then compared hybrid couplings to all-classical Schwarz at high Péclet number (qualitative; held-out cases). I extended the same coupling to time-dependent problems over successive time windows.

The science directions follow prior work: Celaya et al.’s NINNs, and Schwarz–PINN coupling by [Snyder, Tezaur, and Wentland (2023)](https://arxiv.org/abs/2311.00224). I engineered the software and ran the campaigns; mentors directed the science choices. I did not invent NINNs, PocketNet, or Schwarz–PINN.

## HiOp GPU/RAJA driver (LLNL, Summer 2025)

During a scientific computing internship at Lawrence Livermore National Laboratory, I worked in **HiOp** (a high-performance optimization library), using **RAJA** (a portability layer for parallel loops on CPUs and GPUs).

I implemented a RAJA-based dense-constraint **driver** with MPI in HiOp, so the same code path can run on CPU and NVIDIA GPU backends. I added GPU memory-space options and **MAGMA** GPU linear-algebra paths for limited-memory quasi-Newton components, **alongside** existing LAPACK CPU paths. I implemented device-agnostic vector and matrix kernels with RAJA parallel loops and unified memory for host–device movement in HiOp’s linear algebra layer. I configured GPU builds and tests on LLNL’s **Lassen** supercomputer (IBM Power9 + NVIDIA V100) with CMake, automated `ctest`, and `jsrun` job launches, and I debugged GPU code with **TotalView**. The workflow used Git feature branching, code reviews, and Umpire.

## Earlier explorations (2023–2024)

Before focusing on neural PDE solvers, I studied discontinuous Galerkin formulations for coupled flow and deformation in porous media, and I explored phase-field models of fracture. Those were early numerical-method studies, not the current dissertation.

## Dynamical systems and cosmology (SJSU M.S.)

During my M.S. at San José State University, advised by **Dr. Slobodan Simić**, I applied dynamical systems methods to cosmological models in general relativity, including stability analysis of the ΛCDM model.

## Publications and theses

- **Master’s thesis.** Jorge Chumbipuma. *Numerics-Informed Neural Networks for Parabolic Partial Differential Equations*. M.A. thesis, Department of Computational Applied Mathematics and Operations Research, Rice University, conferred 9 May 2026 (defended 9 December 2025). Advisor: Beatrice Riviere.
- **Manuscript in preparation.** Jorge Chumbipuma, Adrian Celaya, and Beatrice Riviere. Numerics-informed neural networks for parabolic equations (working title).
- **Related foundational work (not my authorship).** Adrian Celaya, Keegan Kirk, David Fuentes, and Beatrice Riviere. [Solutions to elliptic and parabolic problems via finite difference based unsupervised small linear convolutional neural networks](https://doi.org/10.1016/j.camwa.2024.08.013). *Computers & Mathematics with Applications*, 174:31–42, 2024. Also [arXiv:2311.00259](https://arxiv.org/abs/2311.00259). Introduces the NINN methodology that the thesis and ongoing work extend.
