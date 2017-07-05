---
author: remy
comments: false
layout: post
slug: irreversibility
title: Dissipation to conservative irreversiblity
categories:
- science
---

It was quite a revelation for me to understand that a linear time-invariant _dissipative_ state-space system

$$
	\begin{equation}
		\dot x = (J-R) x
	\end{equation}
$$

with $J = -J^T$ and $R = R^T$

is equivalent to an _irreversible_ _modulated_ conservative Poisson system

$$
	\begin{equation}
		\dot X = J(X) X
	\end{equation}
$$

In higher dimension, by extending the state vector $$x$$ to $$X = [x, S]$$ by accumulating the dissipated energy into an entropy-like variable $$S$$.