---
title:  "non-negative R.Vs"
mathjax: true
layout: post
---

*Taken from COMS 4995-1 S20 Homework 0, Columbia University*. 

Let X be a non-negative integer-valued random variable.
(a) Prove that $Pr(X \neq 0) \leq \mathbb{E}(X)$.

## Solution

Two approaches:

1) Use Markov's Inequality, i.e. for any non-negative Random Variable (R.V) $X$, the following inequality holds: $P(X \geq a) \leq \frac{\mathbb{E}(X)}{a}$.

Notice that 

$$
\begin{align*}
P(X \neq 0) &= P(X \geq 1) \\
&= \frac{\mathbb{E}(X)}{1} \\
&= \mathbb{E}(X),
\end{align*}
$$
as desired. 


2) Use the "complementary" CDF, i.e. for any non-negative R.V. X, we have $\mathbb{E}(X) = \sum_{x=0}^\infty F^c(x)$, where we define $F^c(x) = \sum_{t=x}^\infty p_x(t)$.

With this fact, we have

$$
\begin{align*}
$$
