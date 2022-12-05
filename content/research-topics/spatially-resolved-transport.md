---

date: 2021-06-02T14:00:00+06:00
lastmod: 2022-07-27T14:00:00+06:00
title: Spatially Resolved Transport
authors: ["georgiosvarnavides"]
slug: spatially-resolved-transport
comments: true
publications:
  - Phys Rev B, 100, 115402 (2019)
  - arXiv:2204.06004 (2022)
thumbnail: /images/research-interest-03.svg
cover:
  image: /images/research-interest-03-cover.svg
  alternate: Schematic of the strain-mismatch model for phonon scattering across semi-coherent interfaces
  caption: Strain Mismatch Model schematic. Black (White) contours illustrate contours of constant compression (tension). 
  style: full

---

During the course of my PhD, I developed an open-source software package called [SpaRTaNS](https://narang-lab.github.io/spartans/) to perform spatially-resolved transport by solving the steady-state Boltzmann transport equation in three real-space and three momentum-space dimensions.

SpaRTaNS is "carrier-agnostic" with applications in phonon (heat) transport (e.g [thermal interface resistance of semi-coherent interfaces]({{< ref "/publications/phys-rev-b-100-115402-2019" >}})), as-well as electron (charge) transport (e.g [the importance of microscopic interactions in electron hydrodynamic flows]({{< ref "/publications/arxiv2204.06004-2022" >}})).
SpaRTaNS can be run on anything from a laptop to high-performance computing systems, and provides a flexible API for specifying custom boundary conditions, collision operators, geometries, state spaces, and more.
