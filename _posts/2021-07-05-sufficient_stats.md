---
title:  "Another random exercise"
mathjax: true
layout: post
---

*Taken from Decentralized Data Reduction with Quantization
Constraints, by Ge Xu, Shengyu Zhu, and Biao Chen*. 

"For the conditional independence case, it can be easily established that local sufficiency implies global sufficiency [7]–
[9]". 

A fun attempt:

## Solution

To make this proof, we make use of the Fisher-Neyman Factorisation Theorem, i.e. Given a likelihood function $f(X \mid \theta)$, $T$ is a sufficient statistic iff there exist non-negative functions $h$ and $g$ such that the likelihood can be factorised in the following manner:
$$
\begin{align*}
f(X \mid \theta) &= f(X, T \mid \theta) \\
&= h(X \mid T, \theta ) \times g(T \mid \theta) \\
&= h(X \mid T) \times g(T \mid \theta).
\end{align*}
$$


$$
\begin{align*}
f(X_1, X_2 \mid \theta) &= f(X_1 \mid \theta) \times f(X_2 \mid \theta) \\
&= f(X_1, T(X_1) \mid \theta) \times f(X_2, T(X_2)  \mid \theta) \\
&= \bigg(f(X_1 \mid T(X_1)) h[g(X_1) \mid \theta] \bigg) \times \bigg(f(X_2 \mid T(X_2)) h[g(X_2) \mid \theta] \bigg) \\
&= 
\end{align*}
$$
