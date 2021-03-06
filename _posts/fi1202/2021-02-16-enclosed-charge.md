---
layout: post
author: viridi
title: enclosed charge
mathjax: true
ptext: false
x3dom: false
threejs: false
oo: false
category: physics
tags: ["electric field", "line of charge", "around"]
date: 2021-02-16 23:40 +07
permalink: /fi1202/enclosed-charge
---
Amount of charge enclosed by Gaussian surface is the enclosed charge [[1](#ref1), [2](#ref2)], where it can be assessed by mapping the electric field on a closed surface outside the charge distribution using Gauss's law [[3](#ref3)]. Some illustrations are given and discussed here.


## fraction, one, or multiple charges
Enclosed charge can consist of fraction of one charge, one charge, or multiple charges. It depends on the Gaussian surface that covers the charge(s).
 
{:refdef: style="text-align: center;"}
![..](/assets/img/phys/electrostatics/qenc/half-sphere-in-box.png)
<br />
Figure <a name="fig:ec-half-sphere-in-box">1</a> A charge $Q$ (left), enclosed charge $q_{\rm enc}$ is a whole charge $Q$ (center), and enclosed charge $q_{\rm enc}$ is half of the charge $\frac12 Q$.
{: refdef}

A whole charge or fraction of one charge enclosed by a Gaussian surface is given in Fig. <a href="#fig:ec-half-sphere-in-box">1</a>, where $q_{\rm enc}$ is simple part of charge that is inside the Gaussian surface (a closed surface). Result of $q_{\rm enc}$ in Fig. <a href="#fig:ec-half-sphere-in-box">1</a> (center) can be obtained using Gauss's law, indeed spherical charge distribution with cubic Gaussian surface, but you will face a very difficult integral, which is not recommended [[4](#ref4)]. We can also draw the Gaussian surfaces in illustrative way to show the concept as given in Fig. <a href="#fig:ec-qenc-surface-concept">2</a>

{:refdef: style="text-align: center;"}
![..](/assets/img/phys/electrostatics/qenc/qenc-surface-concept.png)
<br />
Figure <a name="fig:ec-qenc-surface-concept">2</a> Some charges ($q_1$, $q_2$, $q_3$, $q_4$, $q_5$) and some Gaussian surfaces ($s_1$, $s_2$, $s_3$, $s_4$, $s_5$).
{: refdef}

We can have from Fig. <a href="#fig:ec-qenc-surface-concept">2</a> that enclosed charge $q_{\rm enc}$ by Gaussian surface $s_3$ (green dashed line) is $q_3 + q_4 = +2Q + (-Q) = +Q$. If you like to have a 3-d Gaussian surface, again a cubic surface, but with a real problem, let us take the Fig. <a href="#fig:ec-cell-sc-bcc">3</a> as example.

{:refdef: style="text-align: center;"}
![..](/assets/img/phys/electrostatics/qenc/cell-sc-bcc.png)
<br />
Figure <a name="fig:ec-cell-sc-bcc">3</a> Two varieties of the cubic crystal system: simple cubic (left) and body-centered cubic (right).
{: refdef}

In cubic crystal system there are simple cubic (SC) and body-centered cubic (BCC), whichh area two of three main varieties of the cubic crystal system [[5](#ref5)]. If each single sphere represents a charge $Q$ then in the SC we can have that $q_{\rm enc} = Q$ with cubic Gaussian surface as shown in previous figure. Can you see that?


## spherical charge distribution
By choosing a homogeneous and isotropic material [[6](#ref6)] we will illustrate the enclosed charge $q_{\rm enc}$ from a spherical charge distribution when we use a spherical Gaussian surface. Two system are discussed, which are solid and hollow spheres.

### solid sphere
{:refdef: style="text-align: center;"}
![..](/assets/img/phys/electrostatics/qenc/sphere-in-sphere.png)
<br />
Figure <a name="fig:ec-sphere-in-sphere">4</a> Spherial Gaussian surface of a spherical charge distribution.
{: refdef}

Enclosed charge of the system is

\begin{equation}
\label{eqn:ec-solid-sphere-homogeneous-isotropic}
q_{\rm enc} = \left\\{
\begin{array}{lr}
\displaystyle \left( \frac{r^3}{R^3} \right) Q, & 0 \le r \le R, \newline
Q, & R < r,
\end{array}
\right.,
\end{equation}

where $r$ is radius of the spherical Gaussian surface and $R$ is radius of the sphere.

### hollow sphere
{:refdef: style="text-align: center;"}
![..](/assets/img/phys/electrostatics/qenc/hollow-sphere-in-sphere.png)
<br />
Figure <a name="fig:ec-hollow-sphere-in-sphere">5</a> Spherial Gaussian surface for charge distribution of hollow sphere.
{: refdef}

For this system the enclosed charge is

\begin{equation}
\label{eqn:ec-hollow-sphere-homogeneous-isotropic}
q_{\rm enc} = \left\\{
\begin{array}{lr}
0, & 0 \le r < R_1, \newline
\displaystyle \left( \frac{r^3 - R_1^3}{R_2^3 - R_1^3} \right) Q, & R_1 \le r \le R_2, \newline
Q, & R < r,
\end{array}
\right.,
\end{equation}

where $r$ is radius of the spherical Gaussian surface, $R_1$ and $R_2$ are inner and outter radii of the hollow sphere, respectively.

### formulation
Enclosed charge can obtained using

\begin{equation}
\label{eqn:ec-enclosed-charge}
q_{\rm enc} = \int \rho dV = \int \rho(r) \ r^2 dr \int \sin\theta d\theta \int d\varphi = 4\pi \int \rho(r) \ r^2 dr,
\end{equation}

where $\rho = \rho(r)$ is volume charge density, which can be function of radius $r$. Then for solid sphere 

\begin{equation}
\label{eqn:ec-solid-sphere-homogeneous-isotropic-rho}
\rho(r) = \left\\{
\begin{array}{lr}
\displaystyle \frac{Q}{V}, & 0 \le r \le R, \newline
0, & R < r,
\end{array}
\right.,
\end{equation}

while for hollow sphere

\begin{equation}
\label{eqn:ec-hollow-sphere-homogeneous-isotropic-rho}
\rho(r) = \left\\{
\begin{array}{lr}
0, & 0 \le r < R_1, \newline
\displaystyle \frac{3Q}{4\pi (R_2^3 - R_1^3)}, & R_1 \le r \le R_2, \newline
0, & R < r,
\end{array}
\right.,
\end{equation}

with $r$, $R$, $R_1$, and $R_2$ as in Eqns. \eqref{eqn:ec-solid-sphere-homogeneous-isotropic} and \eqref{eqn:ec-hollow-sphere-homogeneous-isotropic}.


## exercises
1. Using cubic Gaussian surface in Fig. <a href="#fig:ec-half-sphere-in-box">1</a>, where is the position of the sphere to get $q_{\rm enc} = \frac18 Q$ exactly? Explain in brief.
2. Why is it not recommended to get the enclosed charge $q_{\rm enc}$ in Fig. <a href="#fig:ec-half-sphere-in-box">1</a> (center) using a cubic Gaussian surface? See [[4](#ref4)] if necessary to find the answer.
3. From Fig. <a href="#fig:ec-qenc-surface-concept">2</a> find enclosed charge $q_{\rm enc}$ for Gaussian surface $s_1$ and $s_4$. Show how you come the the answers.
4. Find the $q_{\rm enc}$ for BCC in Fig. <a href="#fig:ec-cell-sc-bcc">3</a> (right) with the given cubic Gaussian surface. Explain why you give the answer.
5. Show how to obtain Eqn. \eqref{eqn:ec-solid-sphere-homogeneous-isotropic-rho} using Eqn. \eqref{eqn:ec-enclosed-charge}.
6. Using Eqn. \eqref{eqn:ec-enclosed-charge}, try to derive Eqn. \eqref{eqn:ec-hollow-sphere-homogeneous-isotropic-rho}.
7. In Eqns. Eqn. \eqref{eqn:ec-solid-sphere-homogeneous-isotropic-rho} and Eqn. \eqref{eqn:ec-hollow-sphere-homogeneous-isotropic-rho} how the relation between radius range, e.g. $0 \le r \le R$ and lower and upper bounds of the integral? Explain in brief.
8. How do you obtain the factor $Q/V$ in Eqn. \eqref{eqn:ec-solid-sphere-homogeneous-isotropic-rho}?
9. In Eqn. \eqref{eqn:ec-hollow-sphere-homogeneous-isotropic-rho} there is a factor $\frac{3Q}{4\pi (R_2^3 - R_1^3)}$. Explain how to produce it.
10. Why are $\rho = 0$ out of the spherical systems in Figs. <a href="#fig:ec-solid-sphere-in-sphere">4</a> and <a href="#fig:ec-hollow-sphere-in-sphere">5</a>?


## references
1. <a name="ref1"></a>OpenStax, "6.4: Applyig Gauss's Law", Physics LibreTexts, 6 Nov 2020, url <https://phys.libretexts.org/Bookshelves/University_Physics/Book%3A_University_Physics_(OpenStax)/Map%3A_University_Physics_II_-_Thermodynamics_Electricity_and_Magnetism_(OpenStax)/06%3A_Gauss's_Law/6.04%3A_Applying_Gausss_Law> [20210216].
2. <a name="ref2"></a>Wikipedia contributors, "Gaussian surface", Wikipedia, The Free Encyclopedia, 15 Nov 2020, 22:24 UTC, url <https://en.wikipedia.org/w/index.php?oldid=988897483> [20210216].
3. <a name="ref3"></a>Carl R. Nave, "Gauss's Law", HyperPhysics, 2017, url <http://hyperphysics.phy-astr.gsu.edu/hbase/electric/gaulaw.html> [20210216].
4. <a name="ref4"></a>Michel van Biezen, "Physics - Gauss' Law (11 of 11) Cubic Gaussian Surface", YouTube, 12.03.2014, url <https://www.youtube.com/watch?v=MM-3sgswY9Q> [20210216].
5. <a name="ref5"></a>Wikipedia contributors, "Cubic crystal system", Wikipedia, The Free Encyclopedia, 31 Jan 2021, 02:31 UTC, url <https://en.wikipedia.org/w/index.php?oldid=1003869020> [20210216].
6. <a name="ref6"></a>Gregory Hawkins, "2.1 Basics of the Relativistic Cosmology: the Dynamics of the Universe", SlidePlayer, 2019, p. 14, url <https://slideplayer.com/slide/13942333/> [20210216].

+ [Article history](https://github.com/butiran/butiran.github.io/commits/master/_posts/fi1202/2021-02-16-enclosed-charge.md)
