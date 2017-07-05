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

where $$J = -J^T$$ is a skew-symmetric matrix that has an energy conservation role and $$R = R^T$$ is a symmetric positive definite matrix that has th Rayleigh dissipation rate $$x^T R x$$, is equivalent to an _irreversible_ _modulated_ conservative Poisson system

$$
	\begin{equation}
		\dot X = J(X) X
	\end{equation}
$$

in higher dimension. 

Indeed, by extending the state vector $$x$$ to $$X = [x, S]^T$$ by accumulating the dissipated energy into an entropy-like variable $$S$$.