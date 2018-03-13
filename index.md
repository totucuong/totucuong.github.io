---
layout: page
title: Bayesian data analysis and more.

---

I notice that it is often hard to see the relationship between machine learning algorithms. In this blog, I will write tutorial about diffrent topics and explain how they are related to each other. Most of the theory are drawn from the book Pattern Recognition and Machine Learning by Bishop and the demo will be written in Python notebook.

What does this mean by doing data analysis? The statistician Box suggest the following process:

![Box loop](/assets/gfx/box_model.png)

I will illustrate this process in different Python notebooks as follows.


- Building models
	- [Hierarchical (Multilevel) model]
	- [Latent (hidden) probabilistic models: GMM, k-means, etc.](/pages/demos/em.html)
	- Linear models for regression/classification
	- Neural networks
	- Probablistic graphical networks
- Infer hidden quantities:
	- Variation inference
	- Sampling methods : 
		- Importance sampling
		- MCMC sampling: Metropolis-Hastings, Gibbs, and Hamiltonian MC.
- Apply model:
	- Perform prediction
	- Data exploration
	- Deploying models via REST API.
- Critize model:
	- using posertior predictive checks



