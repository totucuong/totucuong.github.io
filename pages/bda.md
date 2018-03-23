---
layout: page
title: Machine Learning
description: A blog about machine learning techniques and their applications
---

It is often hard to see the relationship among machine learning methods. For example, one can view the popular k-means clustering algorithm as an instance of expectation maximization, which, again, can be viewed as a special case ariational inference. 

Moreover when you learn a method such expectation maximization, or MCMC sampling methods, you can spend hours to understand the mathematics behind them. Yet, when it comes to implementation, it is not so clear how those formulas can be materialized into code.

This motivates me to write a series of Python notebooks to document my knowledge about machine learning methods, their relationship with each other, and, more importantly, their applications. 

Most of the mathematics are drawn from:

 1. Pattern Recognition and Machine Learning, Bishop.
 2. An Introduction to MCMC for Machine Learning, C. Andrieu, et al.
 3. Build, Compute, Critique, Repeat: Data Analysis with Latent Variable Models, David M. Blei.
 4. A Conceptual Introduction to Hamiltonian Monte Carlo, Michael Betancourt.
 5. CS231n: Convolutional Neural Networks for Visual Recognition, Stanford.

Please note that the notebooks' content was derived from a lot of sources and modified by me to reflect my own understanding. Even though, I try to give credits to the original source as much as possible, it is almost certain that I will miss something. I ask for your forgiveness in advance.


What does this mean by doing data analysis? The statistician Box suggest the following process:

![Box loop](/assets/gfx/box_model.png)

I will illustrate this process in the following Python notebooks:


- [Expectation maximization](/pages/demos/em.html)
- Approximiate inference:
	- [Variational inference](/pages/demos/variational_inference.html)
	- [Sampling methods](/pages/demos/MCMC_inference.html) 
- [Prior constructions](/pages/demos/prior_construction.html)
- Case studies:
	- [Porto taxi trajectory clustering](/pages/demos/porto.html)
	- [Facebook check-ins prediction](/pages/demos/facebook.html)
	- [Some fun geo-visualization stuff](/pages/demos/towers.html)