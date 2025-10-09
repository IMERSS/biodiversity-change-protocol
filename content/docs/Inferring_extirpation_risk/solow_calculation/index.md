---
title: Solow calculation (Prior I)
description: Calculating extirpation probabilities based on sighting rates
math: true
categories: [Examples, Placeholders]
tags: [test, docs]
weight: 2
---

## Inferring local extinction based on limited occurrence data

To estimate how likely a species is still present before considering any new evidence, we use a method developed by Solow (1993). This approach starts from the simple idea that the timing of past sightings contains information about whether a species has disappeared. If a species was last observed long ago, and we’ve continued searching without finding it again, our confidence in its persistence naturally declines. 

Solow’s method expresses this intuition mathematically by comparing three key times: 

* T₀ — the beginning of formal record-keeping or the earliest time we could reasonably have detected the species if it were present.
* T₁ — the time of the most recent confirmed sighting
* T₂ — the current time or the endpoint of our study. 

The formula calculates an odds ratio (called a Bayes factor) that weighs the likelihood the species is still present versus extinct, based on how long it has gone unobserved. 

Intuitively, the longer the gap between the last sighting and today (T₂ – T₁), relative to the total observation period (T₂ – T₀), the lower the odds that the species persists. 

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
