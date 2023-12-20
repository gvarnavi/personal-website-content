---

date: 2023-12-19T14:00:00+06:00
lastmod: 2023-12-19T14:00:00+06:00
title: MRS Fall 2023 - 3D Inverse Scattering Problems
authors: ["georgiosvarnavides"]
categories:
  - presentations
slug: mrs23-inverse-scattering-problems
comments: true
thumbnail: /images/presentations-04.png
cover:
  image: /images/presentations-04-cover.png
  alternate: 
  caption: Joint ptychographic tomography single-particle analysis of biological samples schematic.
  style: full

---

**Georgios Varnavides**, Stephanie Ribet, Reed Yalisove, Joel Moore, Colin Ophus, Mary Scott.

2023 Nov 29, [Interactive presentation link](https://gvarnavides.com/2023mrs-presentation/)

#### Abstract

Accelerated electrons passing through a thin sample acquire Aharonov-Bohm phase shifts due to sample interactions which scatter the incident electron wavefunction. These include coherent sources such as electrostatic scattering off atomic columns and scattering against a magnetic vector potential, as-well as incoherent sources such as thermal diffuse scattering and plasmon excitations. Despite the large mechanistic differences between these scattering sources the fact that they are simultaneously collected as far-field diffraction intensities, as-well as the large order of magnitude difference in the acquired phase shifts, suggests the signals are hard to deconvolve. Reconstructing these various scattering sources from diffraction intensities is thus a high-dimensional non-convex inverse problem.  

Electron ptychography is a recently rekindled phase-retrieval technique which attempts to solve this inverse problem using the redundant information in a set of converged-beam diffraction intensities with sufficient real-space illumination overlap, e.g., using a defocused 4DSTEM experiment. Here, we introduce a general framework, implemented in the open-source analysis toolkit py4DSTEM, to reconstruct common coherent and incoherent scattering sources in materials using physically inspired forward and adjoint operators. We illustrate the utility of the framework by jointly reconstructing the coherent electrostatic potential and magnetic vector potential of an anti-ferromagnetically ordered NiO sphere with atomic resolution, as well as elucidating the real-space character of incoherent thermal diffuse scattering.  

We demonstrate how the usual projection-limitation of electron microscopy can be overcome by solving a joint inverse problem for two orthogonal tilt-series directly to obtain the three-dimensional nature of scalar and vector scattering sources such as electrostatic and magnetic vector potentials, respectively. Finally, we investigate the role of optimizing common experimental parameters such as convergence angle, scan step-size, and illuminating probe defocus on the reconstruction quality. 

2023 Nov 29, [Interactive presentation link](https://gvarnavides.com/2023mrs-presentation/)
