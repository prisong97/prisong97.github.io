---
title:  "non-negative R.Vs"
mathjax: true
layout: post
---

*Taken from COMS 4995-1 S20 Homework 0, Columbia University*. 

Let X be a non-negative integer-valued random variable.

(a) Prove that $Pr(X \neq 0) \leq \mathbb{E}(X)$.

### Solution

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
P(X \neq 0) &= \sum_{x=1}^\infty p_(x) \\
&= \mathbb{E}(X) - \bigg(F^c(0) + \sum_{x=2}^\infty F^c(x)\bigg) \\
&\leq \mathbb{E}(X).
\end{align*}
$$

b) Prove that $Pr(X=0) \leq \frac{Var(X)}{\mathbb{E}(X^2)}$.

### Solution

$$
\begin{align}
P(X=0) &= P(X-\mathbb{E}(X) = -\mathbb{E}(X)) \\
&\leq P\big( (X-\mathbb{E}(X))^2 = (\mathbb{E}(X))^2 \big) \\
&\leq P\big( (X-\mathbb{E}(X))^2 \geq (\mathbb{E}(X))^2 \big) \\
&\leq \frac{\mathbb{E}\big[(X- \mathbb{E}(X)\big]^2}{\big[\mathbb{E}(X)\big]^2}.
\end{align}
$$

Notice that $\mathbb{E}(X^2) \geq \big[\mathbb{E}(X)\big]^2$, so 
