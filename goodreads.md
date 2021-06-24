---
title: "Interesting Reads"
permalink: "/goodreads/"
layout: page
---

## To come

"ICU Mortality Prediction: A Classification
Algorithm for Imbalanced Datasets"

- An interesting read! I've been thinking about imbalanced learning for a while. Although there are algorithmic techniques to deal with imbalanced datasets, such as oversampling the minority class, performing SMOTE etc., these quick fixes tend to alter the training set's distribution. Consequently, the training set and testing set end up having different distributions, violating a fundamental modelling assumption. In the case of classification, this might not cause the model's discriminative power to suffer, but might however result in model miscalibration. If we were to view the output of the classifier in a probabilistic light, model miscalibration might then be a cause of concern. How might we try to solve this problem of "imbalanced learning" while maintaining the distributions of the positive-negative class?
- This paper frames the task of classification as a hypothesis-testing problem. By transforming gaussian random variables into chi-square random variables, the positive-negative class distributions are preserved, while making class separation more apparent!
