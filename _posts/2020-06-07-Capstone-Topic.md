---
title: "Capstone Topic"
layout: post
---

In statistical modelling, it is convenient to make the simplifying assumption that observations come from a single parametric distribution. However, this might not always make sense. For instance, in the case of modelling Singaporeans’ heights, we might first guess the existence of two peaks representing males and females in the distribution. Evidently, this model would be insufficiently represented by a standard parametric distribution, such as a unimodal gaussian. Consequently, we turn to more complex models for a more nuanced and realistic representation of the distribution of interest.

In my Capstone, I will be reviewing and comparing different methods for fitting mixture models. In a mixture model, observations are assumed to arise from one of M (finite or infinite) groups, where each group is modelled by a density typically from a parametric family. This model offers a conceptually flexible way of approximating distributions that cannot be satisfactorily modelled by a standard parametric family, as in the case of representing Singaporeans’ heights. For purposes of modelling, we often assume that each of the M groups is a latent variable, and subsequently seek to learn their distributions by estimating these distributions’ parameters. 






