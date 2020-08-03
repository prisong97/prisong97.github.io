---
title: "E-M Algorithm"
mathjax: true
layout: post
---
Assuming that our observations arise from one or more unobserved classes, the Expectation-Maximisation (EM) algorithm iteratively finds the maximum likelihood estimates of these classes’ parameters.

As a motivating example, let us consider a random variable X and a set of $m$ i.i.d observations $\{x\_1, x\_2, \ldots, x\_m \}$. The probability of receiving observation x_i is P(x_i | \theta), where \theta refers to the parameter governing the pdf of distribution X. If we know that X comprises of n subpopulations, then each class \in {1,…,n} and \sum P(z\in Z) = 1. 
