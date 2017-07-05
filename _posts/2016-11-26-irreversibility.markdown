---
author: remy
comments: false
layout: post
slug: irreversibility
title: Dissipation to conservative irreversiblity
categories:
- science
---

It was quite a revelation for me to understand that a linear time-invariant _dissipative_ state-space system of the form

$$
	\begin{equation}
		\dot x = (J-R) x
	\end{equation}
$$

where $$J = -J^T$$ is a skew-symmetric matrix that has an energy conservation role and $$R = R^T$$ is a symmetric positive definite matrix that has the Rayleigh dissipation rate $$x^T R x$$, is equivalent to an _irreversible_ _modulated_ conservative Poisson system

$$
	\begin{equation}
		\dot X = J(X) X
	\end{equation}
$$

in higher dimension. 

Indeed, by extending the state vector $$x$$ to $$X = [x, S]^T$$ and by accumulating the dissipated energy into an entropy-like variable $$S$$.

To make it easier to understand let's use a damped harmonic oscillator. The equivalent in mechanics would be a mass-spring system with friction and in electronics an parallel RLC circuit. It has the following dynamic equation

$$
	\begin{equation}
	\left[\begin{matrix} \dot x \\ \dot y\end{matrix}\right] = \left(\omega \left[\begin{matrix}0 & -1 \\  1 & 0 \end{matrix}\right] - \sigma \left[\begin{matrix}1 & 0 \\ 0 & 0 \end{matrix}\right] \right)\left[\begin{matrix} x \\ y\end{matrix}\right]
	\end{equation}
$$

with energy dissipation rate $$\sigma$$

$$
	\begin{equation}
		\dot E = -\sigma x^2
	\end{equation}
$$