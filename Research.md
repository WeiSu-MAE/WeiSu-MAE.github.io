---
layout: page
title: RESEARCH
permalink: /research/
---

## General Synthetic Iterative Scheme (GSIS) for Multiscale Simulation

![Regime](/public/img/FlowRegimes.png)

Multiscale rarefied gas flows spanning a wide range of Knudsen number are widely encountered in engineering problems, e.g. high-altitude aerothermodynamics of space vehicles, micro-electromechnical systems, and gas transport in ultra-tight shale strata. One of the centeral problems in studying rarefied gas dynamics is to quickly find the steady-state solution of the kinetic equations with considerable accuracy. We put forward a general synthetic iterative scheme (GSIS), which has the capacity to find steady states of gas flows within dozens of iterations at any Knudsen number. The key ingradient of our scheme is that a set of macroscopic equations are simultaneously solved with the kinetic equations, from which the macroscopic quantities are obtained to expedite the evolution of velocity distribution function towards the final solution. Due to the fact that the constitutive equations for shear tensor and heat flux explicity contain not only the Navier-Stokes relations but also the high-order terms exactly drived from the kinetic equation, GSIS can achieve fast convergence and remove the constraint on cell size for small-Knudsen-number flow, while remain accuracy as the rarefaction effect intensifies.


> [<u>LEARN MORE</u>](https://doi.org/10.1016/j.jcp.2020.109245) W Su, L Zhu, P Wang, Y Zhang, L Wu. Can we find steady-state solutions to multiscale rarefied gas flows within dozens of iterations? *Journal of Computational Physics*, 407: 109245,  (2020)
> 
> [<u>LEARN MORE</u>](https://www.researchgate.net/publication/340859948_General_synthetic_iteration_scheme_for_non-linear_gas_kinetic_simulation_of_multi-scale_rarefied_gas_flows) L Zhu, X Pi, W Su, Y Zhang, L Wu. General synthetic iteration scheme for non-linear gas kinetic simulation of multi-scale rarefied gas flows, (2020)

### Fast Convergence and asymptotic preserving

![convergence](/public/img/SR_mod_2.svg)

Rigorous Fourier stability analysis shows that the maximum value of convergence rate (spectral radius $$\omega$$) for GSIS can be less than 0.5. This means that the scheme can reduce the difference of solutions between two successive iterative steps by at least three orders of magnitude only after 10 iterations, allowing fast convergence over the whole flow regime.

![!TwoCylinder](/public/img/TwoCylinderD1000.png)

Through the Chapman-Enskog expansion, we demonstrate that the macroscopic synthetic equations are reduced to the Navier-Stokes equations when the Knudsen number approaches zero, if the spatial cell size is adequate to resolve the hydrodynamic behaviors. The property of asymptotic preserving guarantees GSIS to obtain accurate solution for small-Knudsen-number flows on spatial cell size much larger than the mean free path of gas molecules.

> [<u>LEARN MORE</u>](https://www.researchgate.net/publication/344187324_Fast_convergence_and_asymptotic_preserving_of_the_General_Synthetic_Iterative_Scheme) W Su, L Zhu, L Wu. Fast convergence and asymptotic preserving of the general synthetic iterative scheme. *SIAM Journal on Scientific Computing*, (2020)

### Extension to molecular gases with internal molecular structures

![Transpiration](/public/img/1DTranspiration.svg)

Considering non-vibrational molecular gas flows, in the macroscopic synthetic equations, while the momentum equation is the same as that used in the GSIS for monatomic gas, two energy equations are introduced here for polyatomic gases: one is for the translational energy and the other for internal energy; these equations are derived exactly from the gas kinetic equation hence no approximation is made in the final solution.

![Streamline](/public/img/streamlines.png)

The extented GSIS is a promising tool to simulate multiscale molecular gas flows and investiate the effects of internal degrees of freedom.

> [<u>LEARN MORE</u>](https://www.researchgate.net/publication/344070470_Multiscale_simulation_of_molecular_gas_flows_by_the_general_synthetic_iterative_scheme) W Su, Y Zhang, L Wu. Multiscale simulation of molecular gas flows by the general synthetic iterative scheme,  (2020)

-----------------------------
## High-Order Discontinuous Galerkin Method for Kinetic Equations and Macroscopic Equations

### Implicit DG scheme for kinetic equations

![Mach5](/public/img/Mach5.svg)

![Mach5](/public/img/Beam.svg)

Compared to the Navier-Stokes equations, numerical simulation of the kinetic equation is expensive in terms terms of computation time and memory, since additional dimensions of the molecular velocity space are discretzed. High-order CFD approach is critical to improve efficiency of discretization, thus reduce the computational cost. One of the promising methods for this purpose is the discontinuous Galerkin (DG) method. The explicit Runge-Kutta DG method has been applied to solve the kinetic model equation, where the 2nd-order DG method is 15 times faster than the 2nd-order finite volume method. However, higher-order RKDG scheme is not superior to the lower-order one, due to the restriction on the time step by the CFL condition. 

I develop an implicit DG scheme for the Boltzmann equation with full collision operator, where the DG discretization is incorporated into the fast spectral method to evaluate the collision integral. The proposed scheme can remove the limitatiioin on time step, as a result, the superiority of high-order discretization is reflected. The strategy based on the sweeping technique for solutions of the local linear systems resulting from DG discretization is introduced to avoid assembling large system, and stabilize the scheme without using any nonlinear limiter when high-speed rarefied gas flow is considered.

> [<u>LEARN MORE</u>](https://doi.org/10.1007/s10915-020-01139-7) W Su, P Wang, Y Zhang, L Wu. Implicit discontinuous Galerkin method for the Boltzmann equation with full collision operator. *Journal of Scientific Computing*, 82: 39, (2020).
>
> [<u>LEARN MORE</u>](https://doi.org/10.1016/j.compfluid.2014.12.015) W Su, A Alexeenko, G Cai. A parallel Runge-Kutta discontinuous Galerkin solver for rarefied gas flows based on 2D Boltzmann kinetic equations. *Computers & Fluids*, 109: 123-136, (2015). 

### HDG scheme for macroscopic equations

I also develop the hybridizable DG scheme for the solution of synthetic equations in GSIS.

> [<u>LEARN MORE</u>](https://doi.org/10.1016/j.jcp.2020.109245) W Su, L Zhu, P Wang, Y Zhang, L Wu. Can we find steady-state solutions to multiscale rarefied gas flows within dozens of iterations? *Journal of Computational Physics*, 407: 109245,  (2020)
> 
> [<u>LEARN MORE</u>](https://www.researchgate.net/publication/344070470_Multiscale_simulation_of_molecular_gas_flows_by_the_general_synthetic_iterative_scheme) W Su, Y Zhang, L Wu. Multiscale simulation of molecular gas flows by the general synthetic iterative scheme,  (2020)
> 
> [<u>LEARN MORE</u>](https://doi.org/10.1016/j.jcp.2018.08.050) W Su, P Wang, Y Zhang, L Wu. A high-order hybridizable discontinuous Galerkin method with fast convergence to steady-state solutions of the gas kinetic equation. *Journal of Computational Physics*, 376: 973-991, (2019).

-----------------------------
## Physics of Rarefied Gas Flows

### Velocity slip coefficients

![coeff](/public/img/demo.svg)

Slip-flow theory enables the continued use of the Navier-Stokes description as the Knudsen number increases: the Navier-Stokes solutions remain valid in the bulk provided the velocity slip and temperature jump coefficients; the kinetic effects that are only important within a layer of thickness with several molecular mean free path are accounted by the Knudsen layer functions. By solving the Couette flow and thermal creep flow based on the kinetic equations, we investigate the influences of intermolecular potentials and gas-surface interactions (implemented by the Maxwell and Cercignani-Lampis boundary conditions) on the viscous and thermal slip coefficients and Knudsen layer functions. The influence of intermolecular structures in polyatomic gases on the thermal slip is also investigated. Based on the results, accommodation coefficients in experiments are extracted. 

> [<u>LEARN MORE</u>](https://doi.org/10.1063/5.0018505): P Wang, W Su, L Wu. Thermal transpiration in molecular gas. *Physics of Fluids*, 32: 082005, (2020).
> 
> [<u>LEARN MORE</u>](https://doi.org/10.1016/j.jcp.2018.11.015): W Su, P Wang, H Liu, L Wu. Accurate and efficient computation of the Boltzmann equation for Couette flow: influence of intermolecular potentials on Knudsen layer function and viscous slip coefficient. *Journal of Computational Physics*, 378: 573-590, (2019)

### Apparent gas permeability of porous media

![PorousMedia](/public/img/field_Carpet3.svg)

The apparent gas permeability (AGP) of a porous media is an important parameter to predctt prodcution of unconventional gas. Due to the difficulty in defining the characteristic flow length in complex porous media, the slope in the Klinkenberg correlation varies significantly for different geometries such that a universal expression seems impossible. In this work, by solving the gas kinetic equation using GSIS, we compute the AGP of porous media that are represented by Sierpinski fractals and pore body/throat systems. A new definition of the characteristic flow length is proposed as a func- tion of porosity, tortuosity and intrinsic permeability of porous media, which enables to find a unique slope in the Klinkenberg correlation for all the considered geometries. This research also shows that the lattice Boltzmann method using simple wall scaling for the effective shear viscosity is not able to predict the AGP.

> [<u>LEARN MORE</u>](https://doi.org/10.1016/j.compfluid.2020.104576): W Su, M T Ho, Y Zhang, L Wu. GSIS: an efficient and accurate numerical method to obtain the apparent gas permeability of porous media. *Computers & Fluids*, 206: 104576,(2020)

### Rarefaction Cloaking: Influence of surface roughness in gas slider bearings

![Roughness](/public/img/Roughness.svg)

For ultra-thin gas lubrication, the surface-to-volume ratio increases dramatically when the flow geometry is scaled down to the micro/nano-meter scale, where surface roughness, albeit small, may play an important role in gas slider bearings. However, the effect of surface roughness on the pressure and load capacity of gas slider bearings has been overlooked. In this work, on the basis of the generalized Reynolds equation, we investigate the behavior of a gas slider bearing, where the roughness of the slider surface is characterized by the Weierstrass-Mandelbrot fractal function. Results show that the surface roughness reduces the local mass flow rate as compared to the smooth channel, but the amount of reduction varies for Couette and Poiseuille flows at different Knudsen numbers. As a consequence, a novel “rarefaction cloaking” effect is found, where the load capacity of a rough bearing equals to that of a smooth bearing at a certain range of Knudsen numbers, as if the roughness does not exist.

> [<u>LEARN MORE</u>](https://doi.org/10.1063/1.4999696): W Su, H Liu, Y Zhang, L Wu. Rarefaction cloaking: Influence of the fractal rough surface in gas slider bearings. *Physics of Fluids*, 29: 102003, (2017)

### Rarefied flow separation in microchannel with bends

![bends](/public/img/figAb.png)

The separation of rarefied gas flow in a microchannel with double rectangular bends is investigated over a wide range of Knudsen and Reynolds numbers. The roles of rarefaction effects in vortex formation at the concave and convex corners are revealed. The mass flow rate ratio between the bent and straight channels of the same length is obtained as a function of Knudsen number. The results clarify the diversified and often contradictory observations reported in the literatture about the flow rate enhancement and vortex formation in bent microchannels.

> [<u>LEARN MORE</u>](https://doi.org/10.1017/jfm.2020.585): M T Ho, J Li, W Su, L Wu, M Borg, Y Zhang. Rarefied flow separation in microchannel with bends. *Journal of Fluid Mechanics*, 901: A26, (2020).

-----------------------------
## Nonequilibrium Thermo-Chemical Ralaxation in Shock-Heated Air

![reentry](/public/img/reentry.svg)![Shock-Heated-Air](/public/img/Temp_Con_806.png)

In the context of space exploration, understanding the physico-chemical phenomena that dictate the flow around re-entry capsules allows optimal design of aerodynamic shape and heat shield to fulfill the playload and cost budget, key to success of ambitious missions. Although considerable progress has been accomplished since the 1950s, large uncertanties still remain in the current models for prediction in engineering. In this work a vibration-specific approach is employed to describe vibrational relaxation and reactive processes in shock-heated air. Two sets of rate coefficients for the Zeldovich reactions of NO formation, derived from quasi-classical trajectory calculations, are compared. The effect of the adopted kinetic description on the radiative signature of post-shock plasma is also investigated. Comparison to shock-tube absolute intensity measurements has provided indications for improving nonequilibrium flow modeling.

> [<u>LEARN MORE</u>](https://doi.org/10.2514/1.T5271): W Su, D Bruno, Y Babou. State-specific modeling of vibrational relaxation and nitric oxide formation in shock-heated air. *Journal of Thermophysics and Heat Transfer*, 32: 337-352, (2017)
