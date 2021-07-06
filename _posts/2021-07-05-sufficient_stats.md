---
title:  "An exercise on Sufficiency"
mathjax: true
layout: post
---

*Taken from Decentralized Data Reduction with Quantization
Constraints, by Ge Xu, Shengyu Zhu, and Biao Chen*. 

"For the conditional independence case, it can be easily established that local sufficiency implies global sufficiency [7]–
[9]". 

A fun attempt:

## Solution

To make this proof, we make use of the Fisher-Neyman Factorisation (FN) Theorem, i.e. Given a likelihood function $f(X \mid \theta)$, $T$ is a sufficient statistic for $\theta$ iff there exist non-negative functions $h$ and $g$ such that the likelihood can be factorised in the following manner:


$$
\begin{align*}
f(X \mid \theta) &= f(X, T \mid \theta) \\
&= h(X \mid T, \theta ) \times g(T \mid \theta) \\
&= h(X \mid T) \times g(T \mid \theta).
\end{align*}
$$

To avoid notational clutter, let us denote the local sufficient statistic of $\theta$ (about $X_1$) as $T_1$, and that of $\theta$ (about $X_2$) as $T_2$. Now, we have

$$
\begin{align}
q\big(X_1, X_2 \mid \theta\big) &= f\big(X_1 \mid \theta\big) \times f\big(X_2 \mid \theta\big) &\text{ (by conditional independence) } \\
&= f\big(X_1, T_1 \mid \theta\big) \times f\big(X_2, T_2  \mid \theta\big) \\
&= \bigg(f\big(X_1 \mid T_1\big) h[T_1 \mid \theta] \bigg) \times \bigg(f\big(X_2 \mid T_2\big) h[T_2 \mid \theta] \bigg) &\text{ (by FN factorisation) } \\
&= \bigg(f\big(X_1 \mid T_1, T_2\big) \times \big(f(X_2 \mid T_1, T_2\big) \bigg) p[T_1, T_2 \mid \theta] \\
&= l\big(X_1, X_2 \mid T_1, T_2\big) \times p[T_1, T_2 \mid \theta] ,
\end{align}
$$
as desired. Note that for (4), we made use of the fact that sufficient statistics are not unique: if $T_1$ is sufficient for $\theta$, then $T_1, T_2$ are jointly sufficient for $\theta$. 


Assuming conditional independence, the converse holds true. The proof to this can be found in the paper. 

### A proof sketch:

While the paper makes use of properties of markov chains to illustrate this, we shall do this using the definition of (minimal) sufficiency:

Let $T_1$ and $T_2$ be functions of $X_1$ and $X_2$ respectively.

Without loss of generality, let us assume that a (local) sufficient statistic of $\theta$ (w.r.t. $X_1$) exists, and denote this statistic by $S$. Under mild conditions, we can assume that $S$ is minimally sufficient. For contradiction, further assume that there does not exist a function $u$ such that $S = u(T_1)$, but there exists a function $k$ such that $S = k(T_1, T_2)$. We know the latter condition holds true since $(T_1, T_2)$ are globally sufficient for $\theta$.

By the definition of local sufficiency, $S$ is defined in terms of $X_1$, and is hence independent of $X_2$, given $\theta$. This means tha we can define a new function $h$ such that $h(T_1) = k(T_1, T_2) = S$. However, this contradicts our initial assumption that no such function can exist (coined as $u$). 

Thus, assuming conditional independence, global sufficiency implies local sufficiency.
