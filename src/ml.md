# Scientific machine learning

I have been increasingly interested in ML/AI, particularly in integrating mathematical and physical structures into neural networks. Scientific machine learning (SciML) offers a promising approach to tackling problems where traditional numerical algorithms fall short. For instance, when designed properly, SciML can provide an alternative method for studying dynamical systems.


## Fast neural Poincaré maps for toroidal magnetic fields

![](img/gallery/rmp.png)
Poincaré maps for toroidal magnetic fields are routinely employed to study gross confinement properties in devices built to contain hot plasmas. In most practical applications, evaluating a Poincaré map requires numerical integration of a magnetic field line, a process that can be slow and that cannot be easily accelerated using parallel computations. We propose a novel neural network architecture, the HénonNet,[^1] and show that it is capable of accurately learning realistic Poincaré maps from observations of a conventional field-line-following algorithm. After training, such learned Poincaré maps evaluate much faster than the field-line integration method. Moreover, the HénonNet architecture exactly reproduces the primary physics constraint imposed on field-line Poincaré maps: flux preservation. This structure-preserving property is the consequence of each layer in a HénonNet being a symplectic map. We demonstrate empirically that a HénonNet can learn to mock the confinement properties of a large magnetic island by using coiled hyperbolic invariant manifolds to produce a sticky chaotic region at the desired island location. This suggests a novel approach to designing magnetic fields with good confinement properties that may be more flexible than ensuring confinement using KAM tori.

## Other structure-preserving SciML work

The recent representative papers include: physics-assisted learning,[^2] dynamics learing for multiscale ODEs[^3] or large-scale PDEs,[^4] learning flow maps for multiscale Hamiltonians.[^5] Please refer to the following references for more details. I plan to write more on this topic when I have more time. 


[^1]: J. W. Burby, Q. Tang and R. Maulik. Fast neural Poincare maps for toroidal magnetic fields, **Plasma Physics and Controlled Fusion**, 63:024001, 2020.
[^2]: X. Xie, Q. Tang, and X.-Z. Tang. Physics-assisted latent space dynamics learning for stiff collisional-radiative models, _submitted_, 26 pages, 2024.
[^3]: D. Serino, A. Alvarez Loya, J. W. Burby, I. G. Kevrekidis, and Q. Tang. Intelligent attractors for singularly perturbed dynamical systems, _submitted_, 32 pages, 2024.
[^4]: A. J. Linot, J. W. Burby, Q. Tang, P. Balaprakash, M. D. Graham, and R. Maulik. Stabilized Neural Ordinary Differential Equations for Long-Time Forecasting of Dynamical Systems, **Journal of Computational Physics**, 474:111838, 2023.
[^5]: V. Duruisseaux, J. W. Burby, and Q. Tang. Approximation of Nearly-Periodic Symplectic Maps via Structure-Preserving Neural Networks, **Scientific Reports**, 13.1:8351, 2023.


<script type="text/x-mathjax-config">MathJax.Hub.Config({TeX: {equationNumbers: {autoNumber: "all"}}, tex2jax: {inlineMath: [['$','$']]}});</script>
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.2/MathJax.js?config=TeX-AMS_HTML"></script>
