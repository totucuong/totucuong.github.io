---
layout: post
title:  "Noisy Gradients"
date:   2019-11-02
author: To Tu Cuong
---
In variational infernce, reinforcement learning, sensitivity analysis, it is very common that the loss function is of a form:

$$E_{p_{\theta}(x)}[f(x)].$$


This loss function is typically minizied using stochastic optimization which requires us to compute its noisy gradients:

$$\nabla_{\theta}E_{p_{\theta}(x)}[f(x)] = E_{p_{\theta}(x)}[h(x)].$$

Notice that the original gradients is rewritten as an expectation of another function $h(x)$, which is called a **surrogacy loss**. This enables us to estimate the original gradient using simulation, i.e., Monte Carlo method. Concretely, we have 

$$\nabla_{\theta}E_{p_{\theta}(x)}[f(x)] = \frac{1}{S} \sum_{s=1}^{S} h(x^{(s)})$$


### Surrogacy Loss $h(x)$


### Variance Reduction