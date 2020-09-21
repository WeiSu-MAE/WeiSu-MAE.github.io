---
layout: post
title:  "General Synthetic Iterative Scheme for Multiscale Simulation"
---

### General Synthetic Iterative Scheme (GSIS)

> Wei Su, Lianhua Zhu, Peng Wang, Yonghao Zhang, Lei Wu. Can we find steady-state solutions to multiscale rarefied gas flows within dozens of iterations? Journal of Computational Physics, 407: 109245, 2020. [DOI: 10.1016/j.jcp.2020.109245](https://doi.org/10.1016/j.jcp.2020.109245)
> 
> Lian Zhu, Xincai Pi, Wei Su, Yonghao Zhang, Lei Wu. General synthetic iteration scheme for non-linear gas kinetic simulation of multi-scale rarefied gas flows, 2020. [[ResearchGate]](https://www.researchgate.net/publication/340859948_General_synthetic_iteration_scheme_for_non-linear_gas_kinetic_simulation_of_multi-scale_rarefied_gas_flows)

Multiscale rarefied gas flows spanning a wide range of Knudsen number have been encountered in many engineering problem, e.g. high-altitude aerothermodynamics of space vehicles, micro-electromechnical systems, and gas transport in ultra-tight shale strata. 

One of the centeral problems in studying multiscale rarefied gas dynamics is to quickly find the steady-state solution of the kinetic equations with considerable accuracy. When the Knudsen number is large, i.e. the system is highly rarefied, the conventoinal iterative scheme (CIS) can lead to convergence within a few iterations. However when the Knudsen number is small, i.e. the flow falls into the near-continuum and/or early slip flow regimes, hundreds of thousands iterations are needed. Worse still, the "converged" solutions are prone to suffuer large numerical dissipation if the cell size of spatial grid is larger than the mean free path of gas molecules. 

* We put forward a general synthetic iterative scheme (GSIS), which has the capacity to find the steady-state solutioins of rarefied gas flows within dozens of iterations at any Knudsen number. The key ingradient of our scheme is that a set of macroscopic equations are simultaneously solved with the kinetic equations, from which the macroscopic quantities such as flow density, bulk velocity, temperature, shear stress and heat flux are obtained to expedite the evolution of velocity distribution function towards the final steady state. Due to the fact that the constitutive equations for shear tensor and heat flux explicity contain not only the Navier-Stokes relations but also the high-order terms exactly drived from the kinetic equation, GSIS can achieve fast convergence and remove the constraint on cell size for small-Knudsen-number flow, while predict accurate results as the rarefaction effect intensifies. 

![PorousFlow](/public/img/field_Carpet3.svg)

(Multiscale simulation by GSIS for flow through porous media)

![GSISvsCIS](/public/img/GSISvsCIS2.svg)

(Comparison of CIS and GSIS in terms of the number of iterations to reach convergence and the obtained volumetric flow rate.)

### Fast Convergence and Asymptotic preserving

> Wei Su, Lianhua Zhu, Lei Wu (2020). Fast convergence and asymptotic preserving of the general synthetic iterative scheme. *SIAM Journal on Scientific Computing*. Accepted. [[ResearchGate]](https://www.researchgate.net/publication/344187324_Fast_convergence_and_asymptotic_preserving_of_the_General_Synthetic_Iterative_Scheme)

![convergence](/public/img/SR_mod_2.svg)

Rigorous Fourier stability analysis shows that the maximum value of convergence rate (spectral radius $$\omega$$) for GSIS can be less than 0.5, provided that a relaxation parameter (with quite large parameter window) for the correction of velocity distribution function from macroscopic quantities is properly chosen. This means that the scheme can reduce the difference of solutions between two successive iterative steps by at least three orders of magnitude only after 10 iterations, allowing fast convergence over the whole flow regime.

Through the Chapman-Enskog expansion, we demonstrate that the macroscopic synthetic equations are reduced to the Navier-Stokes equations when the Knudsen number approaches zero, if the spatial cell size is adequate to resolve the hydrodynamic behaviors. The property of asymptotic preserving guarantees GSIS to obtain accurate solution for small-Knudsen-number flows on spatial cell size much larger than the mean free path of gas molecules.

### Extension to molecular gases with internal molecular structures

> Wei Su, Yonghao Zhang, Lei Wu (2020). Multiscale simulation of molecular gas flows by the general synthetic iterative scheme.  Submitted to *Computer Methods in Applied Mechanics and Engineering* [[ResearchGate]](https://www.researchgate.net/publication/344070470_Multiscale_simulation_of_molecular_gas_flows_by_the_general_synthetic_iterative_scheme)

Considering non-vibrational molecular gas flows, the kinetic model equation developed by Prof. Lei Wu [^1] is adopted, which has the following advatages: 1) it is reduced to the Boltzmann equation for monatomic gas when the exchange of translational and rotational energies is absent, so that the effect of intermolecular potential and the shear viscosity can be considered; 2) transport coefficients including the bulk viscosity, translational and rotational thermal conductivities can be freely adjusted to the experimental measured values. 

[^1]: L. Wu, C. White, T. J. Scanlon, J. M. Reese, Y. Zhang. Journal of Fluid Mechanics 763 (2015) 24–50. [DOI: 10.1017/jfm.2014.632](https://doi.org/10.1017/jfm.2014.632)

In the macroscopic synthetic equations, while the momentum equation is the same as that used in the GSIS for monatomic gas, two energy equations are introduced here for polyatomic gases: one is for the translational energy and the other for internal energy; these equations are derived exactly from the gas kinetic equation hence no approximation is made in the final solution.

![Transpiration](/public/img/1DTranspiration.svg)

(Thermal creep flow in molecular gas between two parallel plates. Comparisons between GSIS and CIS over a range of Knudsen numbers $$\tau\in[0.01,10]$$)

