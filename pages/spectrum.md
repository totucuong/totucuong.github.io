---
layout: page
title: spectrum - A truth discovery library
description: Overview of spectrum's features
---

[Spectrum](https://github.com/totucuong/spectrum) is a library that provides implementation of truth discovery algorithms. The goal of truth discovery is to estimate the correct object values as well as data sources' trustworthiness. An object's value can be discrete or continuous. For example, a person's birthplace has a discrete domain, i.e, the birth location. Whereas a stock price is continuous. 

In general, a truth discovery probablistic model has the following structure

![Probalistic graphical model of truth discovery](/assets/gfx/pgm_truthfinding.pdf)

The number of data sources, $|O|$, and the number of values, $c_{s,o}$, could be of millions. This makes exact infernece on truth discovery models intractable. Therefore, we need to resolve to approximate inferences such as variational inference or MCMC sampling methods.