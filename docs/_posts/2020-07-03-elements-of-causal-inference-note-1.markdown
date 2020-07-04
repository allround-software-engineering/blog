---
layout: post
mathjax: true
title:  "Elements of Causal Inference: Reading Notes 1/N"
date:   2020-07-03 23:53:03 -0700
categories: allround notes causal inference
published: true
---

# Elements of Causal Inference: Reading Notes 1/N

## 1.1 Probability Theory and Statistics

AKA "Machine learning"

Problem forumation: Given observations of random variables, infer the underlying causal structure.

Observations:
- inputs = cases = covariates
- outputs = targets = labels

Critical assumption on observations
- i.i.d. = independent and identically distributed

i.i.d. can be violated if
- distribution on random variable changes
- OR intervention happened

We can answer these questions:

1: Regression:

$$ f(x) = \mathbb{E}[Y | X = x] $$

2: Classification:

$$f(x) = argmax _{y \in Y} P(Y = y | X = x)$, where $Y = {classes} $$

3: Density of $p_{X, Y} $ of $P_{X, Y} $

## 1.2 Learning Theory

Statistical learning is ill-posed:
- Extending $ f(x) $  from seen inputs to unseen inputs is a "leap of faith"

Solution:
- Must make assumptions to estimate $ f(x) $ from seen inputs to unseen inputs
- These assumptions are formalized in terms of *capacity* measure
- In practice, these assumptions translate to chose function class, which incorporate *a priori knowledge*
- In Bayesian approaches, we specify prior distribution over function classes and noise model
- In regularization theory, we construct suitable regularizers to use in optimization problem.

Causal learning is harder than statistical learning because an additional ill-posedness:
- "Even complete knowledge of an observational distribution usually does not determine the underlying causal model"
- Namely the observed distribution does not necessarily correspond to a known causal structure.

### Statistical learning example

- Problem: binary pattern recognition
- Goal: minimize the expected error or risk, over some function class
- Since $P_{X, Y}$ is unknown, need to appeal to an induction principle, such as empirical risk minimization
- This learning is consistent (i.e. converges) only if function class is "small"
- The Vapnik-Chervonenkis (VC) dimension is a measure of the capacity or size of function class.
- "Universal Consistency": convergence of a learning algorithm to the lowest achievable risk with any function. i.e. everything can be learned in the limit of infinite data. It does not imply that every problem is learnable well from finite data, due to the phenomenon of slow rates.
- "Universally consistent" algorithms: nearest neighbor classifiers and Support Vector Machines
- "Phenomenon of slow rates": For any learning algorithm, there exist problems for which the learning rates are arbitrarily slow.

"Deep learning" only works if "the underlying distribution does not differ between training and testing, be it by interventions or other change", "does not provide us with the right means to describe what might change"

## References

- [Elements of Causal Inference - Foundations and Learning Algorithms](https://mitpress.mit.edu/books/elements-causal-inference) by Jonas Peters, Dominik Janzing and Bernhard Schölkopf
