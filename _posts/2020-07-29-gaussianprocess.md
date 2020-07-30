---
title: 'Notes on Gaussian Process'
date: 2020-07-29
permalink: /posts/2020/07/gaussianprocess/
tags:
  - learning
  - Bayesian
  - nonparametric
---

<script id="MathJax-script" async src="<url-to-your-site>/mathjax/tex-chtml.js"></script>

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
\begin{align}
f(x)\sim\mathcal{GP}(m(x),k(x,x'))
\end{align}

It aims to infer the function value $$f(x_*)$$ on a new point $$x_{*}$$ based on the observations $$\mathcal{D}$$. According to the formal definition, the collection $$(f_{\mathcal{D}}, f(x_*))$$ follows a joint Gaussian distribution with 


\begin{align}
& =\nabla_\theta V^\pi(s) \\
=& \nabla_\theta \Big(\sum_{a \in \mathcal{A}} \pi_\theta(a \vert s)Q^\pi(s, a) \Big) & \\
=& \sum_{a \in \mathcal{A}} \Big( \nabla_\theta \pi_\theta(a \vert s)Q^\pi(s, a) + \pi_\theta(a \vert s) \color{red}{\nabla_\theta Q^\pi(s, a)} \Big) & \scriptstyle{\text{; Derivative product rule.}} \\
=& \sum_{a \in \mathcal{A}} \Big( \nabla_\theta \pi_\theta(a \vert s)Q^\pi(s, a) + \pi_\theta(a \vert s) \color{red}{\nabla_\theta \sum_{s', r} P(s',r \vert s,a)(r + V^\pi(s'))} \Big) & \scriptstyle{\text{; Extend } Q^\pi \text{ with future state value.}} \\
=& \sum_{a \in \mathcal{A}} \Big( \nabla_\theta \pi_\theta(a \vert s)Q^\pi(s, a) + \pi_\theta(a \vert s) \color{red}{\sum_{s', r} P(s',r \vert s,a) \nabla_\theta V^\pi(s')} \Big) & \scriptstyle{P(s',r \vert s,a) \text{ or } r \text{ is not a func of }\theta}\\
=& \sum_{a \in \mathcal{A}} \Big( \nabla_\theta \pi_\theta(a \vert s)Q^\pi(s, a) + \pi_\theta(a \vert s) \color{red}{\sum_{s'} P(s' \vert s,a) \nabla_\theta V^\pi(s')} \Big) & \scriptstyle{\text{; Because }  P(s' \vert s, a) = \sum_r P(s', r \vert s, a)}
\end{align}



