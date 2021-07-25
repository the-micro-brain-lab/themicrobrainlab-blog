---
title: "Intro to Differential Equation with Julia"
date: 2021-07-25T10:06:16+02:00
draft: false
categories: [Learning]
tags: [ode, julia]
---


### Ordinary Differential Equations

+ The basic form of an ODE:
$$
    u' = f(u).
$$
More specifically, $u$ is a function of the independent variable $t$, and the derivative of $u$ is a function of $u$ itself and other parameter $p$:
$$
    \frac{du}{dt} = f(u, p, t).
$$
