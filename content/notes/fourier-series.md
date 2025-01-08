---
title: "Fourier Series"
date: 2022-02-07T15:30:20Z
draft: false
categories: [Math]
tags: [fourier]
summary: "Summary of Fourier Series based on the lectures of Prof. Steve Bruton."
---

Reference: Fourier Series Lectures of Prof. [Steve Bruton](https://www.youtube.com/playlist?list=PLMrJAkhIeNNT_Xh3Oy0Y4LTj0Oxo8GqsC)

# Fourier Series Part 1: Intuition

* Vague idea

    A function $f(x)$ can be represented as a series of (sum of) projections of itself onto the orothgonal sine and cosine basic.

* Fundamental

    Any vector $\vec{u}$ in a space of two orthogonal basis $\vec{x}$ and $\vec{y}$ can be presented by $\vec{u} = \vec{u}_{x} + \vec{u}_y$, which is:

    $$
    \begin{cases}
    \text{its projection onto the }\vec{x} \text{ basis: } \vec{u}_x = \langle\vec{u}, \vec{x}\rangle \cdot \dfrac{\vec{x}}{||\vec{x}||^2}, \\\\
    \text{its projection onto the }\vec{y} \text{ basis: } \vec{u}_y = \langle\vec{u}, \vec{y}\rangle \cdot \dfrac{\vec{y}}{||\vec{y}||^2}.
    \end{cases}
    $$

    The dot product presents the magnitude of the projection into the corresponding basis, which is then multiplied with the normalized basic vector $\frac{\vec{x}}{||\vec{x}||^2}$ or $\frac{\vec{y}}{||\vec{y}||^2}$ to form the projected vector on each basis.