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

Gaussian process (GP) is a non-parametric supervised  machine learning method, which has been widely used to model nonlinear system dynamics as well.  GP works to infer an unknown function $$y = f(x)$$ based on the training set $$\mathcal{D}:= \{(x_i, y_i): i=1,\cdots,n\}$$ with $$n$$ noisy observations. Comparing with other machine learning techniques, GP has the following main merits: 

- GP provides an estimate of uncertainty or confidence in the predictions through the predictive variance, in addition to using the predictive mean as the prediction.

- GP can work well with small datasets.

- In the nature of Bayesian learning, GP incorporates prior domain knowledge of the unknwon system by defining kernel covariance function or setting  hyperparameters.

Formally, a GP is defined as a collection of random variables, any Gaussian process finite number of which have a joint Gaussian distribution. A GP is fully specified by a mean function $$m(x)$$ and a (kernel) covariance function $$k(x,x')$$, which is denoted as 
\begin{align*}
f(x)\sim\mathcal{GP}(m(x),k(x,x'))
\end{align*}




