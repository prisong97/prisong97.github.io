---
title:  "Another random exercise"
mathjax: true
layout: post
---

*Taken from Robustness and Generalization, by Huan Xu and Shie Mannor*. This is a simple exercise to check that I'm understanding the statement correctly:

The following holds by the Breteganolle-Huber-Carol inequality (cf Proposition A6.6 of van der Vaart and Wellner,
2000):

$$
Pr(\sum_{i=1}^K \left| \frac{\mid N_i \mid}{n} - \mu(C_i) \right| \geq \lambda) \leq 2^K \exp{(\frac{-n\lambda^2}{2})}.
$$

Hence, the following holds with probability at least $1 − \delta$,

$$\sum_{i=1}^K \left| \frac{\mid N_i \mid}{n} - \mu(C_i) \right| \leq \sqrt{\frac{2K\ln{2} + 2\ln{\frac{1}{\delta}}}{n}}.
$$

### Solution

The aforementioned is equivalent to the statement

$$
Pr(\sum_{i=1}^K \mid \frac{\mid N_i \mid}{n} - \mu(C_i) \mid \geq \sqrt{\frac{2K\ln{2} + 2\ln{\frac{1}{\delta}}}{n}}) \leq \delta.
$$

We want to find an expression in terms of $\lambda$ such that 

$$
2^K \exp{\frac{-n\lambda^2}{2}} = \delta.
$$

Thus, massaging the expression, we get

$$\begin{align*}
\ln{\bigg[2^K \exp{(\frac{-n\lambda^2}{2})} \bigg]} &= \ln{\delta} \\
K\ln{2} - \frac{n\lambda^2}{2} &= \ln{\delta} \\
2K\ln{2} + 2\ln{\delta^{-1}} &= n\lambda^2 \\
\lambda &= \sqrt{\frac{2K\ln{2} + 2\ln{\frac{1}{\delta}}}{n}},
\end{align*}
$$

as desired.




