# Scientific computing and simulations
My interest in scientific computing centers around multiscale and multiphysics problems. In fusion modeling, both temporal and spatial scales span many orders of magnitude, presenting a rich class of multiscale and multiphysics challenges for numerical algorithms. As a result, a significant portion of my research has focused on developing scalable physics codes for whole-device modeling in magnetic confinement fusion. Additionally, I am interested in computational plasma physics for other applications, such as astrophysics, accelerators, and inertial confinement fusion (ICF).

## Full cold vertical displacement event (VDE) simulation of a major disruption in an ITER-like tokamak reactor

**LA-UR-23-21442. Approved for public release; distribution is unlimited.** 

We consider a multi-domain quasi-static MHD model for force-free plasmas, addressing the coupling between instability in hot plasmas and the magnetic diffusion in the wall region in ITER.
We develop a solver for the quasi-static force-free plasma model above. This solver is based on Mimetic Finite Difference (MFD) method and [PETSc](https://petsc.org)’s  DMStag data structure for staggered grid representations, fully implicit, solved with the Jacobian-free Newton-Krylov and inexact Newton methods with a field-split nested preconditioning strategy.

The MFD solver[^1] is used for simulating the cold vertical displacement events (VDE) of a major disruption in an ITER-like tokamak reactor over the actual plasma current diffusion time.
The first movie shows the evolution of the toroidal current and magnetic field lines over time for isotropic resistivities inside the tokamak subdomains. 
On the other hand, the remaining animations correspond to a setting where the blanket module has an anisotropic resistivity (different values in toroidal and poloidal directions). This setting was employed to simulate the halo and eddy currents inside the tokamak. All the movies are prestend along one selected poloidal plane. 


----

## Result


<video controls preload="metadata" width="100%">
    <source src="../img/gallery/RJ_phi_10fps.mp4" type="video/mp4">
    Sorry, your browser doesn't support embedded videos.
</video>
*The toroidal current and magnetic field lines over time for a full cold VDE simulation ($T_e = 15{\text eV}$)*

<video controls preload="metadata" width="100%">
    <source src="../img/gallery/halo-eddy-current_10fps.mp4" type="video/mp4">
    Sorry, your browser doesn't support embedded videos.
</video>
*Toroidal current and streamlines of poloidal current over time for the halo current simulation ($T_e = 15{\text eV}$)*

<video controls preload="metadata" width="100%">
    <source src="../img/gallery/JxB-force_pol_10fps.mp4" type="video/mp4">
    Sorry, your browser doesn't support embedded videos.
</video>
*Magnitude of poloidal Lorentz force $|| \left((\nabla\times{\mathbf{B}})\times{\mathbf{B}}\right)_{\rm pol}||$ over time for the halo current simulation ($T_e = 15{\text eV}$)*

<video controls preload="metadata" width="100%">
    <source src="../img/gallery/JxB-force_phi_10fps.mp4" type="video/mp4">
    Sorry, your browser doesn't support embedded videos.
</video>
*Toroidal Lorentz force component $ \left((\nabla\times{\mathbf{B}})\times{\mathbf{B}}\right)_{\phi} $ over time for the halo current simulation ($T_e = 15{\text eV}$)*

[^1]: Z. Jorti, Q. Tang, K. Lipnikov and X.-Z. Tang. A mimetic finite difference based quasi-static magnetohydrodynamic solver for force-free plasmas in tokamak disruptions, [arXiv:2303.08337](https://arxiv.org/abs/2303.08337), submitted, 2023.


<script type="text/x-mathjax-config">MathJax.Hub.Config({TeX: {equationNumbers: {autoNumber: "all"}}, tex2jax: {inlineMath: [['$','$']]}});</script>
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.2/MathJax.js?config=TeX-AMS_HTML"></script>
