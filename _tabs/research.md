---
layout: default
icon: fas fa-flask
order: 2
title: Research
---

## Research

<section id="research">
  <!-- Numerics-Informed Neural Networks (NINNs) for PDEs -->
  <div>
    <h3>Numerics-Informed Neural Networks (NINNs) for PDEs</h3>
    <p>
      Under the direction of <strong>Beatrice Riviere</strong>, I study and extend
      <strong>Numerics-Informed Neural Networks (NINNs)</strong> for parabolic PDEs.
      NINNs were introduced by
      <a href="https://doi.org/10.1016/j.camwa.2024.08.013">Celaya, Kirk, Fuentes, and Riviere (2024)</a>
      (<a href="https://arxiv.org/abs/2311.00259">arXiv:2311.00259</a>; code
      <a href="https://github.com/aecelaya/pde-nets">aecelaya/pde-nets</a>) as unsupervised,
      finite-difference–based convolutional solvers. My work adapts and evaluates that
      methodology—rather than inventing NINNs or PINNs—through PyTorch implementations,
      training-schedule studies, and HPC experiments.
    </p>

    <h4>Contributions:</h4>
    <ul>
      <li>Adapted Celaya-style Backward Euler NINNs with boundary lifting (versus penalty BCs) and compact U-Net choices for two-dimensional parabolic problems</li>
      <li>Implemented PyTorch training pipelines and GPU-aware experiment campaigns (including on Rice NOTs), with ablations and reproducible artifacts in <a href="https://github.com/geochum/neural-pde-solvers">neural-pde-solvers</a></li>
      <li>Analyzed error propagation, stability, and convergence across training schedules and test problems, comparing NINNs to PINNs and classical finite-difference time-stepping</li>
      <li>Documented the computational study in an MA thesis (December 2025); a journal manuscript with Adrian Celaya and Beatrice Riviere is in preparation</li>
    </ul>
  </div>

  <!-- Hybrid PDE solvers (Sandia Summer 2026) -->
  <div>
    <h3>Hybrid Neural / Full-Order PDE Coupling (Sandia Summer 2026)</h3>
    <p>
      During a summer internship at Sandia National Laboratories, mentored by
      <strong>Irina Tezaur</strong> and collaborators, I built
      <a href="https://github.com/geochum/pde-solver-lab">pde-solver-lab</a>—a greenfield
      research lab for classical finite differences, overlapping Schwarz iteration,
      FD-NINNs, PINN baselines, and hybrid NINN–FOM studies. The science directions and
      coupling ideas build on prior work, including Celaya et al.’s NINNs and
      Schwarz–PINN coupling by
      <a href="https://arxiv.org/abs/2311.00224">Snyder, Tezaur, and Wentland (2023)</a>.
    </p>

    <h4>Contributions:</h4>
    <ul>
      <li>Designed and implemented the experiment stack (solvers, coupling loops, notebooks, tests, and campaign tooling) used for summer studies</li>
      <li>Reimplemented and validated Celaya-style NINNs in PyTorch as reusable subdomain solvers within hybrid settings</li>
      <li>Ran controlled studies of hybrid NINN–FOM (and related) overlapping Schwarz couplings, including boundary-condition and training/reuse choices directed by mentors</li>
    </ul>
    <p>
      Accurate framing: I engineered the software and executed the campaigns. I did not
      invent NINNs, PocketNet, or Schwarz–PINN coupling.
    </p>
  </div>

  <!-- High-Performance Optimization (LLNL Summer 2025) -->
  <div>
    <h3>High-Performance Optimization (LLNL Summer 2025)</h3>
    <p>
      During my summer internship at Lawrence Livermore National Laboratory, I worked on GPU-enabled optimization in the <strong>HiOp</strong> (High-performance Optimization) framework.
    </p>

    <h4>Contributions:</h4>
    <ul>
      <li>Implemented a RAJA-based nonlinear dense constraint driver and solver with MPI support, enabling portable performance across CPU and NVIDIA GPU backends</li>
      <li>Ported limited-memory quasi-Newton (QN) methods to GPU architectures by threading a memory-space option throughout solver components and replacing CPU-only LAPACK calls with GPU-ready MAGMA and cuSOLVER placeholders</li>
      <li>Refactored HiOp's linear algebra layer to introduce device-agnostic kernels, RAJA parallel loops, and unified memory (UM) support for efficient host–device data movement</li>
      <li>Designed and documented GPU build/test workflows on LLNL's Lassen supercomputer (IBM Power9 + NVIDIA V100), including automated ctest parallel testing and jsrun-based job launches</li>
      <li>Resolved GPU-related issues using TotalView, cuda-memcheck, and RAJA execution policies</li>
      <li>Followed LLNL development practices including Git feature branching, pull requests, code reviews, and Umpire-aware memory management</li>
    </ul>
  </div>

  <!-- Earlier Explorations (2023–2024) -->
  <div>
    <h3>Earlier Explorations (2023–2024)</h3>
    <p>
      Prior to focusing on neural PDE solvers, I explored several numerical methods and applications:
    </p>
    <ul>
      <li>Previously studied discontinuous Galerkin formulations for coupled flow and deformation in porous media.</li>
      <li>Explored phase-field approaches for fracture modeling as part of early numerical method studies.</li>
    </ul>
    <p>
      These explorations continue to inform my perspective on multiscale and multiphysics simulation challenges.
    </p>
  </div>

  <!-- Dynamical Systems and Cosmology (Master's Research) -->
  <div>
    <h3>Dynamical Systems and Cosmology <em>(SJSU Master's Research)</em></h3>
    <p>
      During my master’s studies at San José State University, my research focused on applying dynamical systems theory to cosmological models in general relativity. This work provided a mathematical framework to study the evolution of the universe and analyze the stability of its critical points.
    </p>

    <h4>Focus:</h4>
    <ul>
      <li><strong>Lambda Cold Dark Matter (ΛCDM) Model:</strong> Analyzed the stability of critical points in the ΛCDM model, examining transitions between radiation-dominated, matter-dominated, and dark energy-dominated phases of the universe.</li>
      <li><strong>Geometric Insights:</strong> Used dynamical systems techniques to explore the relationship between geometry and energy in cosmological equations.</li>
      <li><strong>Numerical Simulations:</strong> Conducted simulations to verify theoretical findings and visualize trajectories of the universe’s evolution.</li>
    </ul>

    <h4>Outcomes:</h4>
    <ul>
      <li>Improved understanding of the long-term behavior of cosmological systems in the models studied.</li>
      <li>Explored dynamical-systems techniques for analyzing nonlinear cosmological equations.</li>
    </ul>

    <p>
      This research examined the interplay between mathematics and physics, and continues to inform my work on complex systems in applied mathematics.
    </p>
  </div>

  <!-- Publications & theses -->
  <div>
    <h3>Publications &amp; Theses</h3>
    <ul>
      <li>
        <strong>Master’s thesis.</strong>
        Jorge Chumbipuma.
        <em>Numerics-Informed Neural Networks for Parabolic Partial Differential Equations</em>.
        M.A. thesis, Department of Computational Applied Mathematics and Operations Research, Rice University, December 2025.
        Advisor: Beatrice Riviere.
      </li>
      <li>
        <strong>Manuscript in preparation.</strong>
        Jorge Chumbipuma, Adrian Celaya, and Beatrice Riviere.
        Numerics-informed neural networks for parabolic equations (working title).
      </li>
      <li>
        <strong>Related foundational work (not my authorship).</strong>
        Adrian Celaya, Keegan Kirk, David Fuentes, and Beatrice Riviere.
        <a href="https://doi.org/10.1016/j.camwa.2024.08.013">Solutions to elliptic and parabolic problems via finite difference based unsupervised small linear convolutional neural networks</a>.
        <em>Computers &amp; Mathematics with Applications</em>, 174:31–42, 2024.
        Also <a href="https://arxiv.org/abs/2311.00259">arXiv:2311.00259</a>.
        Introduces the NINN methodology that my thesis and ongoing work extend.
      </li>
    </ul>
  </div>
</section>
