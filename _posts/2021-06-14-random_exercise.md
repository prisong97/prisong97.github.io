---
title:  "A random probability exercise"
mathjax: true
layout: post
---

*Taken from Problem 297 of Five Hundred Mathematical Challenges (Mathematical Association of America, 1996).* This was an optional problem I encountered during one of my courses taken last semester.


In the knockout phase of a football tournament, there are 16 teams of equal skill
that compete in an elimination tournament. This proceeds in a number of rounds in which teams compete in
pairs; any losing team retires from the tournament. What is the probability
that two given teams will compete against each other? Generalize your answer to $2^k$ teams where k is an
arbitrary positive integer.


### Solution

Let us first consider the given example in which there are 16 teams. Let $X_i$ denote the $i^{th}$ team, where $i \in \{1,2,\ldots, 16\}$. We are interested in finding $P(X_i \text{ plays with } X_j)$ for some $i, j \in {1,2,\ldots, 16}$, $i \neq j$. 

We shall consider this by cases.

##### Case 1:
$P(X_i \text{ plays with } X_j \text{ in first round } \mid X_i) = \frac{1}{15}$.

- Why? Given that $X_i$ is fixed, in order for $X_j$ to play with $X_i$, $X_j$ and $X_i$ must share the same parent node. Hence, there is only 1 such arrangement (out of the possible 15) that would give us the desired result.


