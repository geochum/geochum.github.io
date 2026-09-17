---
layout: default
title: About
icon: fas fa-user
order: 1
---

# About

I am Jorge (George) Chumbipuma, a Ph.D. student in Computational & Applied Mathematics at Rice University. My advisor is **Dr. Beatrice Riviere**. I study numerical methods for time-dependent partial differential equations, with a focus on numerics-informed neural solvers. Project writeups, code, and publications are on the [Research](/research/) page.

**Funding.** Current support is the **NDSEG Fellowship** (Department of Defense, September 2025 – August 2028) and the **Ken Kennedy Institute 2025/26 ExxonMobil Graduate Fellowship**. Previously: **GEM Employer Sponsored Fellowship** (National GEM Consortium, sponsored by MIT Lincoln Laboratory, 2024).

## Research interests

I extend **Numerics-Informed Neural Networks (NINNs)** for parabolic PDEs, a method introduced by [Celaya, Kirk, Fuentes, and Riviere (2024)](https://doi.org/10.1016/j.camwa.2024.08.013). The network is trained on a discrete residual with fixed finite-difference operators, and Dirichlet conditions are enforced exactly by **boundary lifting**. The main comparison is classical **Backward Euler** finite differences; physics-informed neural networks (PINNs) are Rice **thesis** baselines. I did not invent NINNs or PINNs. Details are on the [Research](/research/) page.

## Experience

- **R&D Graduate Summer Intern — Computer Science Research Institute (CSRI), Sandia National Laboratories** (Summer 2026)
  I built overlapping-Schwarz software for two-dimensional advection–diffusion: finite-difference or NINN solvers on each subdomain, coupled through interface data, including time-window marching. Mentored by **Dr. Irina Tezaur**.

- **Scientific Computing Intern — Lawrence Livermore National Laboratory** (Summer 2025)
  I implemented a RAJA dense-constraint driver with MPI in HiOp, added MAGMA GPU linear-algebra paths alongside LAPACK, and configured GPU tests on Lassen (IBM Power9 + NVIDIA V100) with `ctest`, `jsrun`, and TotalView.

- **Owl Edge Externship — Computational Science, Oak Ridge National Laboratory** (March 2025)
  I shadowed computational scientists, including a Frontier supercomputer tour, with host **Dr. Shuo Qian**.

- **Summer Research Intern — MIT Lincoln Laboratory** (Summer 2024)
  I built MATLAB models of Intelligence, Surveillance, and Reconnaissance (ISR) and tactical system performance and ran scenario sweeps over mission parameters.

<!-- - **Virtual Math Instructor – Art of Problem Solving (2023–present)**
  Teach middle- and high-school students in courses such as Prealgebra, Algebra, and Precalculus. -->

## Presentations

Selected talks and posters, newest first.

- **Numerics-Informed Neural Networks for PDE Solvers: Error Bounds and Pretrained Models for Schwarz Domain Decomposition** (Oral presentation), Technical Presentation Competition, 50th Annual GEM Conference, Dallas, TX, September 2026
- **Numerics-Informed Neural Networks for Parabolic Partial Differential Equations** (Poster), International Congress of Mathematicians (ICM 2026), Philadelphia, PA, July 2026
- **Numerics-Informed Neural Networks for Parabolic Partial Differential Equations** (Contributed presentation), 2026 SIAM Annual Meeting (AN26), Cleveland, OH, July 2026
- **Numerics-Informed Neural Networks for Parabolic PDEs** (Lightning talk and poster), Energy HPC & AI Conference, Ken Kennedy Institute, Rice University, Houston, TX, February 2026. One of seven selected lightning speakers.
- **Scientific Machine Learning for Geophysical PDEs** (Poster), SIAM Conference on Mathematical & Computational Issues in the Geosciences (GS25), Louisiana State University, Baton Rouge, LA, October 2025

## Leadership, mentoring, and teaching

### Leadership

- **Vice President — Rice University SIAM Student Chapter** (August 2026 – present)
  I serve as Vice President for the 2026–2027 term and maintain the chapter website (events, SIAM meetings, internships and fellowships, and newsletter materials).

### Mentoring

- **Peer Mentor — PhD Peer Mentoring Program**, Rice University Center for Engineering Excellence Through Equity (October 2025 – present)
  I mentor a Ph.D. student in the George R. Brown School of Engineering and Computing through Rice’s formal peer mentoring program.

- **Invited panelist — Fellowship Guidance**, Gulf Coast Undergraduate Research Symposium (GCURS), Rice University (October 2025)
  I represented NDSEG on a fellowship panel with NSF GRFP, Fulbright, Hertz, and Goldwater.

- **Peer Mentor — SACRED Mentoring Program / MAS Circle**, Society for Advancement of Chicanos/Hispanics & Native Americans in Science (SACNAS) (March 2025 – September 2025)
  I mentored a student transitioning to graduate-level mathematics through SACNAS’s Mentorship Activated by SACNISTAs (MAS) Circle.

<!-- - **Participant — Activation 1:1 Coaching Program**, Rice University Doerr Institute for New Leaders (August 2023 — December 2023)
  Completed semester-long, personalized leadership coaching with an ICF-certified coach. Strengthened skills in empathic listening, delegation, trust-building, and emotional intelligence. -->

### Teaching

- **Founder & Lead Educator — Pumatics** (January 2022 – present)
  I run a tutoring service in math, science, computer science, and test preparation. Details are on the [Tutoring](/tutoring/) page.

## Conferences and workshops

Participant-only events (talks are listed under Presentations, not here).

- **SIAM Texas–Louisiana Sectional Meeting** — Participant, Austin, TX, September 2025
- **Scientific Machine Learning for Differential Equations Workshop** — Participant, Oden Institute, Austin, TX, September 2025
- **Firedrake USA 2025 Workshop** — Participant, Waco, TX, February–March 2025
- **Blackwell–Tapia Conference** — Participant, ICERM / Brown University, Providence, RI, November 2024
- **GEM 2024 Annual Conference** — Participant, San Antonio, TX, September 2024
- **SACNAS CareerCon 2024** — Participant, remote, March 2024

## Education

### Rice University, Houston, TX

**Doctor of Philosophy — Computational and Applied Mathematics**
*August 2023 – expected May 2028*
- **Advisor:** Dr. Beatrice Riviere
- **Courses:** Applied Functional Analysis; Advanced Numerical Analysis; Numerical Methods for PDEs; Numerical Linear Algebra; Systems of Equations & Unconstrained Optimization; Modeling Mathematical Physics; High-Performance Computing; Scientific Machine Learning

**Master of Arts — Computational and Applied Mathematics** (thesis)
*August 2023 – May 2026*
- **Thesis:** *Numerics-Informed Neural Networks for Parabolic Partial Differential Equations*
- **Defense:** 9 December 2025
- **Conferred:** 9 May 2026
- **Committee:** Dr. Beatrice Riviere (advisor), Dr. Lu Zhang, Dr. Thomas Anderson

### San José State University, San Jose, CA

**Master of Science — Mathematics**
*August 2020 – August 2022*
- **Advisor:** Dr. Slobodan Simić
- **Honors:** Phi Kappa Phi
- **Courses:** Numerical PDEs; Numerical Linear Algebra; Advanced Dynamical Systems; Stochastic Processes

### University of California, Irvine, Irvine, CA

**Bachelor of Science — Electrical Engineering and Physics** (double major)
*September 2010 – June 2013*
- **Minor:** Information and Computer Science
- **Honors:** Tau Beta Pi
- **Courses:** Numerical Analysis; Data Structures; Digital Signal Processing; Engineering Probability; Computer Organization; Embedded Computing Systems; Statistical Physics; Mathematical Physics

## Future goals

I aim to work as a computational scientist at a national laboratory, building numerical methods and scientific computing software for large-scale simulations.
