---
title:  "Another random exercise"
mathjax: true
layout: post
---

*Taken from Robustness and Generalization, by Huan Xu and Shie Mannor*. This is a simple exercise to check that I'm understanding the statement correctly:

The following holds by the Breteganolle-Huber-Carol inequality (cf Proposition A6.6 of van der Vaart and Wellner,
2000):

$$
Pr(\sum_{i=1}^K \left| \frac{\mid N_i \mid}{n} - \mu(C_i) \right| \geq \lambda) \leq 2^K \exp{\frac{-n\lambda^2}{2}}.
$$

Hence, the following holds with probability at least $1 − \delta$,

$$\sum_{i=1}^K \mid \frac{\mid N_i \mid}{n} - \mu(C_i) \mid \leq \sqrt{\frac{2K\ln{2} + 2\ln{\frac{1}{\delta}}}{n}}.
$$

### Solution

The aforementioned is equivalent to the statement

$$
Pr(\sum_{i=1}^K \mid \frac{\mid N_i \mid}{n} - \mu(C_i) \mid \geq \sqrt{\frac{2K\ln{2} + 2\ln{\frac{1}{\delta}}}{n}}) \leq \delta.
$$





Let us first consider the given example in which there are 16 teams. Let $X_i$ denote the $i^{th}$ team, where $i \in \\{ 1,2,\ldots, 16 \\}$. We are interested in finding $P(X_i \text{ plays with } X_j)$ for some $i, j \in \\{ 1,2,\ldots, 16 \\}$, $i \neq j$. 

In total, this tournament has 4 rounds (round robin, quarter-finals, semi-finals, and finals). This can be illustrated using a binary tree as well. Let us walk through the working, round by round.

##### Case 1:
$P(X_i \text{ plays with } X_j \text{ in first round } \mid X_i) = \frac{1}{15}$.

- Why? Given that $X_i$ is fixed, in order for $X_j$ to play with $X_i$, $X_j$ and $X_i$ must share the same parent node. Hence, there is only 1 such arrangement (out of the possible 15) that would give us the desired result.


##### Case 2:
$P(X_i \text{ plays with } X_j \text{ in second round } \mid X_i) = \frac{1}{2} \times \frac{1}{15}$.

- Consider the following derivation:

$$
\begin{align*}
P(X_i \text{ plays with } X_j \text{ in second round } \mid X_i) &= P(X_i \text{ wins first round })P(X_j \text{ wins first round })P(X_j \text{ in adjacent 'tree' }) \\
&= \frac{1}{2} \times \frac{1}{2} \times \frac{2}{15} \\
&= \frac{1}{2} \times \frac{1}{15}.
\end{align*}
$$

##### Case 3:
$P(X_i \text{ plays with } X_j \text{ in third round } \mid X_i) = \frac{1}{4} \times \frac{1}{15}$.

- The working goes as follows:

$$
\begin{align*}
P(X_i \text{ plays with } X_j \text{ in third round } \mid X_i) &= P(X_i \text{ wins first and second rounds })P(X_j \text{ wins first and second rounds })P(X_j \text{ in adjacent 'tree' }) \\
&= P(X_i \text{ wins first round })P(X_i \text{ wins second round })P(X_j \text{ wins first round })P(X_j \text{ wins second round })P(X_j \text{ in adjacent 'tree' }) \\
&= \bigg(\frac{1}{2}\bigg)^2 \times \bigg(\frac{1}{2}\bigg)^2 \times \frac{4}{15} \\
&= \frac{1}{4} \times \frac{1}{15}.
\end{align*}
$$

##### Case 4:

By a similar argument, we have $P(X_i \text{ plays with } X_j \text{ in fourth round } \mid X_i) = \frac{1}{8} \times \frac{1}{15}$.


By the law of total probability, we can sum these values to get the desired result, i.e.

$$\begin{align*}
P(X_i \text{ plays with } X_j \mid X_i) &= \frac{1}{15} + \bigg( \frac{1}{2} \times \frac{1}{15} \bigg) + \bigg( \frac{1}{4} \times \frac{1}{15} \bigg) + \bigg( \frac{1}{8} \times \frac{1}{15} \bigg)  \\
&= \frac{1}{8}.
\end{align*}
$$

### Generalising this solution

In general, we find that the common (fractional) factor to all constituent terms (corresponding to each round) is $\frac{1}{2^k - 1}$, where $2^k$ represents the total number of teams. In total, there are $k$ rounds. Hence, the generalised formula for the probability is

$$\begin{align*}
P(X_i \text{ plays with } X_j) &= \frac{1}{2^k - 1} \times \sum_{i=0}^{k-1} \frac{1}{2^i} \\
&= \frac{1}{2^k-1} \times \frac{1-(\frac{1}{2})^k}{\frac{1}{2}} \\
&= \frac{2}{2^k-1} \times \frac{2^k - 1}{2^k} \\
&= \frac{1}{2^{k-1}}.
\end{align*} $$
