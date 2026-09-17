---
layout: page
title: Research
icon: fas fa-flask
order: 2
---

> Classical time-stepping for parabolic PDEs is stable, but it becomes expensive on fine grids. Networks trained only on a residual in the continuum — **physics-informed neural networks (PINNs)** — often struggle with discrete structure and boundary conditions. I work on **numerics-informed** solvers: the network is trained on a **discrete residual** of a chosen scheme (in the thesis, Backward Euler with a five-point Laplacian), with exact Dirichlet conditions enforced by **boundary lifting**. At Sandia I reused those pretrained local solvers as subdomain problems inside **overlapping Schwarz** domain decomposition.
{: .prompt-info }

[Projects](#projects) · [Earlier work](#earlier-work) · [Publications](#publications) · [Talks](/about/#talks)
{:.page-jump}

## Research projects
{: #projects}

### Numerics-informed neural networks for parabolic PDEs
{: #ninns}

Rice University · advisor **Dr. Beatrice Riviere**
{:.text-muted}

I extend **Numerics-Informed Neural Networks (NINNs)** for two-dimensional parabolic problems, including the heat equation. NINNs were introduced by [Celaya, Kirk, Fuentes, and Riviere (2024)](https://doi.org/10.1016/j.camwa.2024.08.013){: target="_blank" rel="noopener noreferrer"} ([arXiv:2311.00259](https://arxiv.org/abs/2311.00259){: target="_blank" rel="noopener noreferrer"}; code [aecelaya/pde-nets](https://github.com/aecelaya/pde-nets){: target="_blank" rel="noopener noreferrer"}) as unsupervised, finite-difference–based convolutional solvers.

- **Method.** A compact U-Net is trained on the discrete residual of Backward Euler plus a five-point Laplacian. Dirichlet data enter through boundary lifting rather than penalty terms. I compare this solver to PINNs and to the **same** finite-difference scheme; those PINN baselines are part of the Rice thesis, not the Sandia internship.
- **What I did.** I implemented the PyTorch training pipelines, ran GPU experiments on Rice **NOTS**, and analyzed manufactured-solution error, stability, and convergence across training schedules. On selected smooth problems the NINN shows at least second-order convergence and smaller error than the same finite-difference scheme.
- **Writing.** M.A. thesis, defended 9 December 2025, conferred 9 May 2026. A journal manuscript with Adrian Celaya and Beatrice Riviere is in preparation (working title below).

### Hybrid NINN–FOM overlapping Schwarz
{: #sandia}

Sandia CSRI · Summer 2026 · mentored by **Dr. Irina Tezaur**
{:.text-muted}

**Overlapping Schwarz** iterates on overlapping subdomains coupled through interface data. I built a Python/PyTorch codebase for two-dimensional **advection–diffusion**.

- **Setup.** Each subdomain can be a classical finite-difference full-order model (FOM) or a NINN, coupled through interface data.
- **What I did.** I trained NINNs offline on discrete residual losses with exact Dirichlet conditions and reused them as local solvers instead of retraining every Schwarz iteration. I compared hybrid couplings to all-classical Schwarz at high Péclet number (qualitative; held-out cases), and I extended the same coupling to time-dependent problems over successive time windows.
- **Lineage.** Celaya et al.’s NINNs, and Schwarz–PINN coupling by [Snyder, Tezaur, and Wentland (2023)](https://arxiv.org/abs/2311.00224){: target="_blank" rel="noopener noreferrer"}. I engineered the software and ran the campaigns; mentors directed the science choices.

### HiOp GPU/RAJA driver
{: #llnl}

Lawrence Livermore National Laboratory · Summer 2025
{:.text-muted}

I worked in **HiOp** (a high-performance optimization library), using **RAJA** (a portability layer for parallel loops on CPUs and GPUs).

- **Driver.** I implemented a RAJA-based dense-constraint **driver** with MPI in HiOp, so the same code path can run on CPU and NVIDIA GPU backends.
- **Linear algebra.** I added GPU memory-space options and **MAGMA** GPU paths for limited-memory quasi-Newton components, **alongside** existing LAPACK CPU paths, plus device-agnostic vector and matrix kernels with RAJA parallel loops and unified memory.
- **Platform.** I configured GPU builds and tests on LLNL’s **Lassen** supercomputer (IBM Power9 + NVIDIA V100) with CMake, automated `ctest`, and `jsrun`, and I debugged GPU code with **TotalView**. The workflow used Git feature branching, code reviews, and Umpire.

## Earlier work
{: #earlier-work}

Before focusing on neural PDE solvers, I studied discontinuous Galerkin formulations for coupled flow and deformation in porous media, and I explored phase-field models of fracture. Those were early numerical-method studies, not the current dissertation.

During my M.S. at San José State University, advised by **Dr. Slobodan Simić**, I applied dynamical systems methods to cosmological models in general relativity, including stability analysis of the ΛCDM model.

## Publications and theses
{: #publications}

- **Numerics-Informed Neural Networks for Parabolic Partial Differential Equations.**  
  Jorge Chumbipuma. M.A. thesis, Department of Computational Applied Mathematics and Operations Research, Rice University. Conferred 9 May 2026; defended 9 December 2025. Advisor: Beatrice Riviere.

- **Numerics-informed neural networks for parabolic equations** (working title).  
  Jorge Chumbipuma, Adrian Celaya, and Beatrice Riviere. Manuscript in preparation.

- **Solutions to elliptic and parabolic problems via finite difference based unsupervised small linear convolutional neural networks.**  
  Adrian Celaya, Keegan Kirk, David Fuentes, and Beatrice Riviere. [*Computers & Mathematics with Applications*](https://doi.org/10.1016/j.camwa.2024.08.013){: target="_blank" rel="noopener noreferrer"} 174:31–42, 2024. Also [arXiv:2311.00259](https://arxiv.org/abs/2311.00259){: target="_blank" rel="noopener noreferrer"}.  
  Not my authorship; this paper introduces the NINN methodology that the thesis extends.
  {:.text-muted}
