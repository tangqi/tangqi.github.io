# High-performance computing

I am interested in developing scalable, adaptive, high-order numerical algorithms on exascale computers. I build upon computational techiniques 
such as implicit time stepping, iterative methods, adavanced preconditioning, adaptive mesh refinement, domain decompositions, and GPU accelerations. Here two recent works are presented. 

## Scalable MFEM-based resistive MHD solver

**LA-UR-22-22440. Approved for public release; distribution is unlimited.** 

The magnetohydrodynamics (MHD) equations are continuum models used in the study of a wide range of plasma physics systems, including the evolution of complex plasma dynamics in tokamak disruptions. However, efficient numerical solution methods for MHD are extremely challenging due to disparate time and length scales, strong hyperbolic phenomena, and nonlinearity. Therefore the development of scalable, implicit MHD algorithms and high-resolution adaptive mesh refinement strategies is of considerable importance. 

We recently developed a high-order stabilized finite-element algorithm[^1] for the reduced visco-resistive MHD equations based on [MFEM](https://mfem.org). The scheme is fully implicit, solved with the Jacobian-free Newton-Krylov (JFNK) method with a physics-based preconditioning strategy. Our preconditioning strategy is a generalization of the physics-based preconditioning methods in [Chacon, et al, JCP 2002] to adaptive, stabilized finite elements. Algebraic multigrid methods are used to invert sub-block operators to achieve scalability. A parallel adaptive mesh refinement scheme with dynamic load-balancing is implemented to efficiently resolve the multi-scale spatial features of the system. The potential of the AMR approach is observed in an island coalescence problem in the high Lundquist-number regime ($\ge 10^7$) with the successful resolution of plasmoid instabilities and thin current sheets.

----

## Result

<video controls preload="metadata" width="100%">
    <source src="../img/gallery/res1e-6.mp4" type="video/mp4">
    Sorry, your browser doesn't support embedded videos.
</video>
*This simulation uses 6 levels of AMR refinement, H1 finite elements of 3rd order polynomials, physics-based preconditioning, and stabilized discretization on 1800 CPUs. The run is initialized with two magnetic islands and they collide into each other and form the current sheet. The movie zooms in the center of the entire simulation domain. Here it uses the Lundquist number of $10^6$. Therefore, the plasmoids start to appear around the thin current sheet at a later time, and those plasmoids are quickly ejected into the jet region in the top and bottom of the current sheet.*

----

<video controls preload="metadata" width="100%">
    <source src="../img/gallery/res1e-6-2.mp4" type="video/mp4">
    Sorry, your browser doesn't support embedded videos.
</video>
*Zoomed-in view of the above run around the current sheet*

----

![](img/gallery/mfem-dd.png)
*Domain decomposition at the intial time (left) and the final time (right) of the above run. A random number is assigned to each domain for visualization. Since a space filling curve is used for partitioning, the decompositions are mostly continuous througout the run.*

----

<video controls preload="metadata" width="100%">
    <source src="../img/gallery/res1e-7.mp4" type="video/mp4">
    Sorry, your browser doesn't support embedded videos.
</video>
*This simulation uses 7 levels of AMR refinement and the Lundquist number of $10^7$ instead. The run is also initialized with two magnetic islands and a very thin current sheet is forming in the center. Note that many plasmoids continuously appear around the current sheet particularly near the center of the domain (x point), and those plasmoids collide into each other and form a very complicated structure.*

----

## Adaptive, scalable relativistic Fokker-Planck-Boltzmann solver based on PETSc-p4est 

**LA-UR-22-22439. Approved for public release; distribution is unlimited.** 

We consider a 0D2V relativistic Fokker-Planck equation for runaway electrons[^2]
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

[^1]: Q. Tang\*, L. Chacon, T. V. Kolev, J. N. Shadid and X.-Z. Tang. An adaptive scalable fully implicit algorithm based on stabilized finite element for reduced visco-resistive MHD, **Journal of Computational Physics**, 454:110967, 2022

[^2]: J. Rudi\*, M. Heldman, E. M. Constantinescu, Q. Tang\*, and X.-Z. Tang. Scalable implicit solvers with dynamic mesh adaptation for a relativistic drift-kinetic Fokker–Planck–Boltzmann model, **Journal of Computational Physics**, 507:112954, 2024.


<script type="text/x-mathjax-config">MathJax.Hub.Config({TeX: {equationNumbers: {autoNumber: "all"}}, tex2jax: {inlineMath: [['$','$']]}});</script>
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.2/MathJax.js?config=TeX-AMS_HTML"></script>
