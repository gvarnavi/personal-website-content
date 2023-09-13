---

date: 2023-09-12T14:00:00+06:00
lastmod: 2023-09-12T14:00:00+06:00
title: IMC23 - 3D Imaging of Antiferromagnetism
authors: ["georgiosvarnavides"]
categories:
  - presentations
slug: imc23-imaging-magnetization
comments: true
thumbnail: /images/presentations-03.png
cover:
  image: /images/presentations-03-cover.png
  alternate: 3D NiO Sphere Joint Reconstruction
  caption: Simultaneously-reconstructed magnetic potential of antiferromagnetically ordered NiO sphere.
  style: full

---

**Georgios Varnavides**, Stephanie Ribet, Reed Yalisove, Joel Moore, Colin Ophus, Mary Scott.

2023 Sep 14, [Interactive presentation link](https://gvarnavides.com/2023imc-presentation/)

#### Abstract

An electron beam passing through a thin sample acquires an Aharonov-Bohm phase shift due to the electrostatic potential, V(r), and magnetic vector potential, A(r), of the sample:

{{< katex >}}
\phi(\vec{r}_{\perp}) = \phi_e(\vec{r}_{\perp}) + \phi_m(\vec{r}_{\perp}) = \sigma \int V(\vec{r}_{\perp} + l \hat{\omega}) dl - \frac{e}{\hbar} \int \vec{A}(\vec{r}_{\perp} + l \hat{\omega})\cdot \hat{\omega} dl,
{{< /katex >}} 

where {{< katex inline >}} \sigma {{< /katex >}} is the interaction constant, {{< katex inline >}} e {{< /katex >}} is the elementary charge, {{< katex inline >}} \hbar {{< /katex >}} is the reduced Planck's constant, and {{< katex inline >}} \vec{r}_{\perp} {{< /katex >}} denotes the position vector lying in the plane perpendicular to the beam projection direction {{< katex inline >}} \hat{\omega} {{< /katex >}}.
The large magnitude difference between the two contributions suggests that the magnetic contribution can safely be ignored in conventional (S)TEM imaging and underscores the inherent signal-to-noise challenge of atomic-scale imaging of magnetization.
Recently, several authors have utilized prior knowledge of the magnetic ordering in model systems to enable atomic-scale imaging of magnetization via kernel-filtering and unit-cell averaging of DPC measurements, centre-of-mass and principal component analysis, and Fourier-filtering of ptychographically-reconstructed phase images.


Alternatively, one can attempt to separate the electrostatic and magnetic contributions of the retrieved phase shifts of two sets of measurements, e.g., as performed in off-axis electron holography: 

{{< katex >}}
\phi_e = \frac{1}{2}\left(\phi^{\rightarrow} + \phi^{\leftarrow}\right), \qquad \qquad \phi_m = \frac{1}{2}\left(\phi^{\rightarrow} - \phi^{\leftarrow}\right),
{{< /katex >}} 

where {{< katex inline >}} \phi^{\rightarrow} {{< /katex >}} and {{< katex inline >}} \phi^{\leftarrow} {{< /katex >}} represent obtained phase shifts during “forward” and “reverse” measurements, between which the magnetic contribution is assumed to flip sign.
This can e.g., be achieved by rotating an inversion-symmetric sample 180°.
However, the procedure is prone to noise amplification and relies on the often-impractical restriction of correctly aligning the two measurements.
Figure 1 illustrates this limitation for an anti-ferromagnetically ordered NiO sphere simulated slightly off-axis, using a joint ptychographic reconstruction of the electrostatic and magnetic vector potential contributions.
The projected electrostatic potential (top middle) has been incorrectly “symmetrized” leading to a lower-fidelity subtraction for the projected z-component of the magnetic vector potential (bottom middle). 

Here, we introduce a novel algorithm which attempts to jointly reconstruct the three-dimensional electrostatic potential and vectorial nature of the magnetic potential from two sets of 4D-STEM tilt-series along orthogonal axes.
Our algorithm is implemented in the open-source analysis toolkit py4DSTEM and uses a physically inspired forward model which projects the magnetic vector potential along each tilt-direction.
This enables high signal-to-noise reconstructions, while allowing different constraints on the electrostatic and magnetic potential objects, e.g., positivity on the electrostatic potential and ensuring the magnetic vector potential is divergence-free using the Helmholtz-Hodge decomposition.  

Figure 2 illustrates the performance of the reconstruction algorithm using two full tilt-series (±180° in 12° increments) along the x- and y-directions of the same anti-ferromagnetically ordered NiO sphere simulated off-axis shown in Figure 1. 
Not only are the projected electrostatic and z-component of the magnetic potential reconstructed with higher fidelity, but we recover the vectorial nature of the magnetic potential and electrostatic potential in 3D. 
Finally, we comment on the effect of common experimental limitations such as missing-wedge artifacts and how effective regularization strategies can help remedy these.  

2023 Sep 14, [Interactive presentation link](https://gvarnavides.com/2023imc-presentation/)
