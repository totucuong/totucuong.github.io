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
	- Last but not least, [prior constructions](/pages/demos/prior_construction.html)
- Infer hidden quantities:
	- Variation inference
	- [Sampling methods:](/pages/demos/MCMC_inference.html) 
		- Importance sampling
		- MCMC sampling: Metropolis-Hastings, Gibbs, and Hamiltonian MC.
- Apply model:
	- Perform prediction
	- Data exploration
	- Deploying models via REST API.
- Critize model:
	- using posertior predictive checks


Please note that the notebooks' content was derived from a lot of sources and modified by me to suit my own understanding. I will try to give credits to the original source as much as possible. I ask for your forgiveness if I fail to do so.
