# Adaptive, scalable relativistic Fokker-Planck-Boltzmann solver based on PETSc-p4est 

**LA-UR-22-22439. Approved for public release; distribution is unlimited.** 

## Overview

We consider a 0D2V relativistic Fokker-Planck equation for runaway electrons 
\begin{align}
\frac{\partial f}{\partial t}  - eE_\parallel \left(\xi\frac{\partial f}{\partial p} + \frac{1-\xi^2}{p} \frac{\partial f}{\partial\xi} \right) = C_{\rm col}(f) + C_{\rm rad}(f) + C_{\rm Chiu}(f),
\end{align}
where $C_{\rm col}(f)$ is a Columbo collision operator, $C_{\rm rad}(f)$ a radiation damping operator,
and $C_{\rm Chiu}(f)$ is a secondary knock on collision source.
We develop a scalable fully implicit solver with dynamic adaptivity. We developed a new data management framework in [PETSc](https://petsc.org) based on the [p4est](https://p4est.org) library that enables simulations with dynamic adaptive mesh refinement (AMR), and implemented a new runaway electron solver that interfaces to the PETSc framework. 

----

## Result

<video controls preload="metadata" width="100%">
    <source src="../img/gallery/E_1.69chiu.mp4" type="video/mp4">
    Sorry, your browser doesn't support embedded videos.
</video>
*The simulation demonstrates the critical need for AMR[^1], in which 7 levels of refinement are used (corresponding to a 128 factor of resolution increase) to resolve both low-energy Maxwellian bulk and high-energy runaway tail. The dynamic AMR successfully captures the interaction between two structures and resolves a forming vortex structure. A delta-function-like Chiu source and practical collision parameters extracted from ITER are also deployed.*

<video controls preload="metadata" width="100%">
    <source src="../img/gallery/dd-p4est.mp4" type="video/mp4">
    Sorry, your browser doesn't support embedded videos.
</video>
*MPI Ranks are presented to demonstrate dynamic load balancing. Here 64 CPUs are used in this AMR run. Unlike the MFEM MHD work which uses a Hilbert curve, here a "zig-zag" space filling curve is used which results into discontinuity in domain decompositions.*

[^1]: J. Rudi\*, M. Heldman, E. M. Constantinescu, Q. Tang\*, and X.-Z. Tang. Scalable implicit solvers with dynamic mesh adaptation for a relativistic drift-kinetic Fokker–Planck–Boltzmann model, **Journal of Computational Physics**, 507:112954, 2024.


<script type="text/x-mathjax-config">MathJax.Hub.Config({TeX: {equationNumbers: {autoNumber: "all"}}, tex2jax: {inlineMath: [['$','$']]}});</script>
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.2/MathJax.js?config=TeX-AMS_HTML"></script>
