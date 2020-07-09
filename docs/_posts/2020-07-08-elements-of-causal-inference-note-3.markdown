---
layout: post
mathjax: true
title:  "Elements of Causal Inference: Reading Notes 3/N"
date:   2020-07-08 22:05:26 -0700
categories: allround notes causal inference
published: true
---

# Elements of Causal Inference: Reading Notes 3/N

## 2 Assumptions for Causal Inference

Independence:
- "generic viewpoint assumption in vision: assumes that the object is independent from our vantage point and the illumination. So there should be no unlikely coincidences, no separate 3D structures lining up in two dimensions, or shadow boundaries coinciding with texture boundaries."
- "structure from motion" = "the object and the lighting are not affected by us moving about"
- In SCM, "one module’s output may influence another module’s input, the modules themselves are independent of each other"


## 2.1 The Principle of Independent Mechanisms

$p(a, t)$  can be decomposed into
- $p(a \mid t)p(t)$
- $p(t \mid a)p(a)$

If $A \rightarrow T$ is the correct causal structure, then
- It is in principle possible to **perform a localized intervention** on $A$, in other words, to change $p(a)$ without changing $p(t|a)$
- AND $p(a)$ and $p(t \mid a )$ are **autonomous, modular, or invariant** mechanisms or objects in the world.

Note to self: The second property is exploited in transfer learning. See paper "A Meta-Transfer Objective for Learning to Disentangle Causal Mechanisms" Link to [my slides](/deep-learning/transfer-learning/2019/10/25/meta-transfer-objective.html)

Note to self: The second property can also be thought of as a smaller model that can explain explain the $p(a, t)$ data.

Principle 2.1: (physical) independence of mechanisms, implications:
- intervenability, autonomy, modularity, invariance, transfer
- independence of information contained in mechanisms
- independence of noises, conditional independence of structures

Not all systems will satisfy this. For instance, if the mechanisms that an overall system is composed of have been tuned to each other by design or evolution, this independence may be violated.

This principle is sufficiently broad:
- In physical domain, this principle assumes we can change one mechanism without affecting the others, which is often a fair assumption.
- From information theoretic perspective, this principle implies: the mechanism that generates the effect from its cause contains no information about the mechanism generating the cause.
- Independence of noise terms

## 2.2 Historical Notes

SEM (structural equation models) are nowadays most strongly associated with econometrics.

Simon's invariance criterion: the true causal order is the one that is invariant under the right sort of intervention.

Pearl [2009, p. 104], on connecting Bayesian networks and structural equation modeling:

> It suddenly hit me that the century-old tension between economists and statisticians stems from simple semantic confusion: statisticians read structural equations as statements about $E [Y \mid x]$ while economists read them as $ E[Y \mid do(x)] $.

Pearl [2009, p. 22] formulates the independence principle as follows:

> that each parent-child relationship in the network represents a stable and autonomous physical mechanism - in other words, that it is conceivable to change one such relationship without changing the others.

Most of the work using causal Bayesian networks only exploits the independence of noise terms.


## References

- [Elements of Causal Inference - Foundations and Learning Algorithms](https://mitpress.mit.edu/books/elements-causal-inference) by Jonas Peters, Dominik Janzing and Bernhard Schölkopf
