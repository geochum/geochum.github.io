---
layout: default
icon: fas fa-flask
order: 2
title: Research
---

## Research

<section id="research">
  <!-- Neural-Informed Neural Networks (NINNs) for PDEs -->
  <div>
    <h3>Neural-Informed Neural Networks (NINNs) for PDEs</h3>
    <p>
      My research focuses on scientific machine learning for PDEs—developing NINNs and PINNs architectures and GPU-accelerated simulation. The work addresses algorithmic foundations of optimization, neural network architectures, and uses HPC clusters for large-scale computations.
    </p>

    <h4>Methods:</h4>
    <ul>
      <li>Develop PyTorch-based training pipelines for time-dependent physical systems using deep learning algorithms</li>
      <li>Analyze error propagation, stability, and convergence under varied data and sampling regimes</li>
      <li>Implement GPU-aware experiments (NumPy/PyTorch) with ablations, data science methodologies, and reproducible artifacts</li>
      <li>Compare NINNs against PINNs and finite-difference solvers, focusing on convergence rates and stability</li>
    </ul>

    <p>
      Recent work includes introducing Backward Euler–based NINN architectures using discrete Laplacian operators and compact U-Nets for two-dimensional parabolic PDEs, demonstrating competitive convergence rates and stability with classical finite difference schemes.
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
    <h3>Dynamical Systems and Cosmology <em>(Master's Research)</em></h3>
    <p>
      During my master’s studies at San José State University, my research focused on applying dynamical systems theory to cosmological models in general relativity. This work provided a mathematical framework to study the evolution of the universe and analyze the stability of its critical points.
    </p>

    <h4>Key Contributions:</h4>
    <ul>
      <li><strong>Lambda Cold Dark Matter (ΛCDM) Model:</strong> Analyzed the stability of critical points in the ΛCDM model, examining transitions between radiation-dominated, matter-dominated, and dark energy-dominated phases of the universe.</li>
      <li><strong>Geometric Insights:</strong> Used dynamical systems techniques to explore the relationship between geometry and energy in cosmological equations.</li>
      <li><strong>Numerical Simulations:</strong> Conducted simulations to verify theoretical findings and visualize trajectories of the universe’s evolution.</li>
    </ul>

    <h4>Results:</h4>
    <ul>
      <li>Improved understanding of the long-term behavior of cosmological systems.</li>
      <li>Provided tools for analyzing nonlinear dynamical systems in general relativity.</li>
    </ul>

    <p>
      This research examined the interplay between mathematics and physics, and continues to inform my work on complex systems in applied mathematics.
    </p>
  </div>
</section>
