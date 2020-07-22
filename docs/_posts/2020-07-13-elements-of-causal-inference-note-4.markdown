---
layout: post
mathjax: true
title:  "Elements of Causal Inference: Reading Notes 4/N"
date:   2020-07-13 23:58:15 -0700
categories: allround notes causal inference
published: true
---

# Elements of Causal Inference: Reading Notes 4/N

## 2.3 Physical Structure Underlying Causal Models
### 2.3.1 The Role of Time

In Physics basic laws, causation happens from past to future.

Time ordering can provide a useful asymmetry, it is asymmetry that is important, not the temporal sequence.

### 2.3.2 Physical Laws

The gas law $pV = nRT$ refers to an equilibrium state. It does not provide enough information about what interventions are in principle possible and what is their effect.

### 2.3.3 Cyclic Assignments
For SCMs representing abstractions of underlying processes that take place in time. There is no problem with feedback loops in underlying processes. The loops will unfold in time at most at the finite speed of light.

It is possible to have cycles without time component. Intervention may still be possible, e.g. hard-setting the value of one variable, thereby cutting the cycle.

However, it may be impossible to derive an entailed observational distribution from a cyclic set of structural assignments e.g.:

$$ X := f_{X} (Y, N_{X} ) $$

$$ Y := f_{Y} (X, N_{Y} ) $$

Assuming $ N_{X} \\!\perp\\!\\!\\!\perp N_{Y} $

Equilibrium for X,Y need not always exist, and even if it does, it need not be the case that it can be found using the iteration
In the linear case, this has been analyzed by Lacerda et al. [2008] and Hyttinen et al. [2012]; see also Lauritzen and Richardson [2002]. For further details see Remark 6.5

In this view, SCMs are abstractions of underlying physical processes - abstractions whose domain of validity as causal models is limited.

If we want to understand general cyclic systems, it may be unavoidable to study systems of differential equations rather than SCMs.

### 2.3.4 Feasibility of Interventions

We have used the principle of independent mechanisms to motivate interventions that only affect one mechanism (or structural assignment) at a time.

Real systems often have interventions that replace several assignments at the same time, and these interventions are tuned to each other. This would violate independence Principle 2.1.

One may hope that combined interventions that are "natural" will not violate independence.

### 2.3.5 Independence of Cause and Mechanism and the Thermodynamic Arrow of Time

Principle 2.2 (Initial state and dynamical law) If s is the initial state of a physical system and M a map describing the effect of applying the system dynamics for some fixed time, then s and M are independent. Here, we assume that the initial state, by definition, is a state that has not interacted with the dynamics before.

- Principle 2.2 can also be interpreted as algorithmic independence of s and M.
- Janzing et al. [2016, Theorem 1] show that
  - For any bijective M
  - AND Assuming Kolmogorov complexity (see Section 4.1.9) as the right formalization of physical entropy, as proposed by Bennett [1982] and Zurek [1989]
  - Then Principle 2.2 implies non-decrease of entropy in the sense of the standard arrow of time in physics.
  - AKA The physical entropy of M(s) cannot be smaller than the entropy of s (up to an additive constant).

## References

- [Elements of Causal Inference - Foundations and Learning Algorithms](https://mitpress.mit.edu/books/elements-causal-inference) by Jonas Peters, Dominik Janzing and Bernhard Schölkopf
