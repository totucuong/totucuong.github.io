---
layout: post
title:  "Noisy Gradients I - The Theory"
date:   2019-11-02
author: To Tu Cuong
---
In variational infernce, reinforcement learning, or sensitivity analysis, it is very common that the loss function has the form $E_{p(x;\theta)}[f(x)]$. This loss function is typically minimized using stochastic optimization, which requires us to compute its noisy gradients $\nabla_{\theta}E_{p(x;\theta)}[f(x)] = E_{p(x;\theta)}[h(x)].$ 

In this post, I will only focus on explaining the theory of computing noisy gradients and leave the implementation part to a future post. I also drop a lot of **mundane theortical details**. I feel that this help me to understand the topic better. The readers are referred to the references for more in-depth discussion.


The original gradients is rewritten as an expectation of another function $h(x)$, which is called a **surrogacy loss**. This enables us to estimate the original gradient using simulation, hence, the name **noisy gradients**. 

$$
\begin{align}
\label{eq:1}
\nabla_{\theta}E_{p_{\theta}(x)}[f(x)] = \frac{1}{S} \sum_{s=1}^{S} h(x^{(s)}) \tag{1}
\end{align}
$$


### Differentiation Under an Integral Sign

Let's reconsider the problem of computing $\nabla_{\theta}E_{p(x)}[f(x)]$ (we drop $\theta$ for convenience). We rewrite it as follows.

$$
\begin{align}
\nabla_{\theta}E_{p(x)}[f(x)] &= \nabla_{\theta}\int p(x)f(x)dx
\end{align}
$$

Only some forms of $p(x)$ and $f(x)$ allows use to evaluate analytically the above integration. This makes computing gradients impossible. What if we can interchange integration and differentiation, $\nabla \int \rightarrow \int \nabla$? This will bring us two benefits. First, we can differentiate inside the integration sign using automatic differentiation supported by a lot of popular library such as Autograd, Tensorflow, or PyTorch. Second, we can rewrite integration as an expectation with respect to some probability distribution, which enable us to perform estimation using simulation. It turns out we can do this sort of interchange under some regularity conditions [2] that are quite easy statisfy:

- $p$ is continuosly differentiable wrt $\theta$, i.e., $p^{\prime}(x,\theta)$ is continuous.
- $p*f$ is both differentiable and integrable for all $\theta$.
- there is a function $g(x)$ is integrable and $\vert f(x)\nabla_{\theta}g(x) \vert \leq g(x), \forall x$


### Surrogacy Loss $h(x)$
There multiple type of surrogacy losses which corresponds to different ways of estimate noisy gradients. 
- **score-function** surrogacy loss
- **pathwise** surrogacy loss

#### Score-function estimator

The first type of estimator is **score function** estimator. They are named as such because the surrogacy loss is defined using the score function $\nabla_{\theta}\log p(x;\theta)$:

$$h(x) := f(x) \nabla_{\theta}\log p(x;\theta)$$

Plug the score function surrogacy loss into Equation $\ref{eq:1}$, we have the score function estimator.

#### Pathwise estimator

Remember the popular VAE or reparameterization trick? This is just a different name for pathwise estimator. In pathwise estimator, we focus on sampling path or the path from the noise signal to the data. By reparameterize a distribution: $x \stackrel{reparameterized}{=} g(\epsilon;\theta), \epsilon \sim p(.)$, we have the surrogacy loss function:

$$h(x) :=  \nabla_{\theta}f(g(\epsilon;\theta)))$$

Again plug this into Equation $\ref{eq:1}$, we have the pathwise estimator. But note that the sample now is not $x^{s}$ but rather $\epsilon^{s}} since we reparameterized our original distribution.


### Conclusion

We have discussed basic noisy gradient estimators defined in terms of their corresponding surrogacy loss function. As you may already noticed, an estimation is only good if they satistify the two conditions: (i) unbiased - the expectation of the estimation is the true gradient, (ii) low variance. In the next post, I will discuss more on this aspect and implement both estimators.

### References

1. Monte Carlo Gradient Estimation in Machine Learning, Shakir Mohamed, Mihaela Rosca, Michael Figurnov, Andriy Mnih.

2. Statistical Inference, George Casella and Roger L. Berger.



