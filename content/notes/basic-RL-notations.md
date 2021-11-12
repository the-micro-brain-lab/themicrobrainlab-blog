---
title: "Basic RL Notations"
date: 2021-11-12T11:44:31Z
draft: true
---

# Basic Notations in Reinforcement Learning

## Policy

+ Deterministic policy $a_t = \mu_{\theta}(s_t)$
+ Stochastic policy $a_t \sim \pi_{\theta}(a_t | s_t)$

```mermaid
graph TD;
  A-->B;
  A-->C;
  B-->D;
  C-->D;
```