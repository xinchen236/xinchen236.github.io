---
title: 'Notes on Gaussian Process'
date: 2020-07-29
permalink: /posts/2020/07/gaussianprocess/
tags:
  - learning
  - Bayesian
  - nonparametric
---

My study notes on Gaussian Process and some useful resources.

Useful Resources
------

- GP Toolbox in Matlab: [GPML](http://www.gaussianprocess.org/gpml/code/matlab/doc/). A GP theme website is [here](http://www.gaussianprocess.org/).

- A good GP textbook: [Gaussian Processes for Machine Learning](http://www.gaussianprocess.org/gpml/chapters/RW.pdf).

I. Introduction
======

Gaussian process (GP) is a non-parametric supervised  machine learning method, which has been widely used to model nonlinear system dynamics as well.  GP works to infer an unknown function $$y = f(x)$$ based on the training set $$\mathcal{D}:= \{(x_i, y_i)|\, i=1,\cdots,n\}$$ with $$n$$ noisy observations. 
