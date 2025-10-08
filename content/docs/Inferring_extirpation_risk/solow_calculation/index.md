---
title: Solow calculation (Prior I)
description: Calculating extirpation probabilities based on sighting rates
math: true
categories: [Examples, Placeholders]
tags: [test, docs]
weight: 2
---

## Inferring local extinction based on limited occurrence data

We'll work through the computation of our prior probability of presence (PP) using
[Solow's 1993 formula](https://esajournals.onlinelibrary.wiley.com/doi/10.2307/1940821) for one of our focal species, _Crassula connata_. As is common
for our rare species of interest, we have just one sighting in the historical
record, made in 1983, which time we'll call $T_1$. This requires some care in applying Solow's formula (expand
section below for mathematical details) which formally requires a minimum of two sightings in order
to give meaningful results.

In this case we adopt a "sentinel" earliest sighting $T_0$ corresponding to the beginning
of formal record-keeping in the area, 1958 [AS fill in explanation here], and choose our
project datum $T_2$ as 2019.
In this case, Solow's formula determining the Bayes factor (odds ratio) in favour
of presence simplifies to $B(t) = 1 / [(T_2 - T_0) / (T_1 - T_0) - 1] = 0.6944$.

Transforming from an odds ratio to a probability using the standard formula $P(t) = B(t)/ (1 + B(t))$
gives our prior probability of presence $PP_{CC} = 0.41$.

This could also be 
represented as the prior probability of extinction $PE_{CC} = 1 - PP_{CC} = 0.59$, the figure
appearing in Table 2 in our paper.

<p>
  <a class="btn btn-primary" data-bs-toggle="collapse" href="#collapseExample" role="button" aria-expanded="false" aria-controls="collapseExample">
    Expand for mathematical details
  </a>
</p>
<div class="collapse" id="collapseExample">
  <div class="card card-body">
<p>
Solow (1993) provides a framework for determining a reasonable prior distribution 
for belief about species extinction when observational data are limited. 
Their Equation 3 presents a Bayes Factor for summarizing evidence in favor of extinction, 
given by: \(B(t) = (n - 1) / [(T/t_n )^{(n - 1)} - 1]\) where \(n\) is the number of observations and \(T_i\) 
represents the \(ith\) sighting time and \(T\) is the present date. 
</p>
</div>
</div>
