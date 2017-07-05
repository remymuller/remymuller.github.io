---
author: remy
comments: false
layout: post
slug: irreversibility
title: Conservative Dissipation?
categories:
- science
---

It was quite a revelation for me to understand that a _dissipative_ LTI state-space system of the form

$$
	\begin{equation}
		\dot{\mathbf x} = (J-R) \mathbf x
	\end{equation}
$$

where $$J = -J^T$$ is a skew-symmetric matrix that has an energy conservation role and $$R = R^T$$ is a symmetric positive definite matrix that generates the Rayleigh dissipation rate $$\mathbf x^T R \mathbf x$$, is equivalent to a _nonlinear irreversibly modulated conservative_ Poisson system in higher dimension. 

$$
	\begin{equation}
		\dot{\mathbf X} = J(\mathbf X) \mathbf X
	\end{equation}
$$

by extending the state vector $$\mathbf x$$ with an entropy-like variable $$z$$ that has the role of accumulating the dissipated energy.

To make it easier to understand let's use a damped harmonic oscillator with the following dynamic equation

$$
	\begin{equation}
	\left[\begin{matrix} \dot x \\ \dot y\end{matrix}\right] = \left(\omega \left[\begin{matrix}0 & -1 \\  1 & 0 \end{matrix}\right] - \sigma \left[\begin{matrix}1 & 0 \\ 0 & 0 \end{matrix}\right] \right)\left[\begin{matrix} x \\ y\end{matrix}\right]
	\end{equation}
$$

It has pulsation $$\omega$$ and dissipation $$\sigma$$ and the Hamiltonian energy function 

$$
	H(x,y) = \frac{1}{2} (x^2 + y^2)
$$

with the energy dissipation rate $$\sigma$$

$$
	\begin{equation}
		\dot E = \nabla H(\mathbf x)^T \dot {\mathbf x} = -\sigma x^2
	\end{equation}
$$

The equivalent in mechanics would be a mass-spring system with friction or in electronics a parallel RLC circuit.

Now let's consider the augmented Hamiltonian $$H(x,y,z) = \frac{1}{2}(x^2 + y^2 + z^2)$$. We wish to find the dynamic on $$z$$ in order to have a conservative hamiltonian $$H(x,y,z) = C$$, i.e. $$\frac{d}{dt} H(x,y,z) = 0$$

This is satisfied by

$$
	\begin{equation}
		\left[\begin{matrix} \dot x \\ \dot y \\ \dot z\end{matrix}\right] =  \left[\begin{matrix}0 & -\omega & - \frac{\sigma x}{z} \\  \omega & 0 & 0 \\ \frac{\sigma x}{z} & 0 & 0 \end{matrix}\right] \left[\begin{matrix} x \\ y \\ z\end{matrix}\right]
	\end{equation}
$$

i.e.

$$
	\begin{equation}
		\dot {\mathbf X} = J(\mathbf X) \mathbf X
	\end{equation}
$$

with $$J(\mathbf X) =-J^T(\mathbf X)$$. We have converted a _linear time-invariant dissipative_ problem to a _conservative time-variant_ one on the surface of a sphere. Indeed:

$$
	\begin{align}
		\dot E = \nabla H(\mathbf X)^T \dot{\mathbf X} = -\sigma x^2 + \sigma x^2 = 0 
	\end{align}
$$

The consequence of this, is that any energy-preserving numerical scheme applied to the extended system has the side-effect of preserving the _dissipative invariant_

The energy is indeed conserved and transmitted _irreversibly_ toward the $$z$$ coordinate

![]({{ site.url }}/images/irreversibility/time_series.png){:width="640"}

The decay rate is also better approximated with this approach compared to the Trapezoidal rule simulation

![]({{ site.url }}/images/irreversibility/energy_decay.png){:width="640"}
