---
title: Solow calculation (Prior I)
description: Calculating extirpation probabilities based on sighting rates
math: true
categories: [Examples, Placeholders]
tags: [test, docs]
weight: 2
---

## Inferring local extinction based on limited occurrence data

To estimate the likelihood of a species presence before considering any new evidence, 
we use a non-parametric extinction test—a method developed by Solow (1993).
This approach starts from the simple idea that the timing of past sightings contains 
information about whether a species might have disappeared. If a species was last observed 
long ago, and we’ve continued searching without finding it again, our confidence in 
its persistence declines. 

Solow’s method expresses this intuition mathematically by comparing three key times, for
a species that has been observed $n$ times during an observation period: 

* $T_0$ — the beginning of formal record-keeping, or the earliest 
time we could reasonably have detected the species if it were present
* $t_n$ — the time of the most recent confirmed sighting
* $T$ — the current time or the endpoint of our study 

The formula calculates an odds ratio (called a Bayes factor) that weighs the 
likelihood that the species is still present versus extinct, based on how long it has 
gone unobserved. The smaller the time between the last sighting and today $(t_n - T_0)$, 
relative to the total observation period $(T - T_0)$, the lower the odds that the 
species persists. 

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
given by: \(B(t) = (n - 1) / [((T - T_0)/(t_n - T_0))^{(n - 1)} - 1]\) where \(n\) is the number of 
observations, \(t_i\) represents the \(ith\) sighting time, \(T\) is the present date and \(T_0\) is
the start of the period of observation.
</p>
<p>
In the case \(n = 1\) this formula simplifies to 
\(B(t) = 1 / ln((T - T_0)/(t_n - T_0))\).
</p>


Here is an interactive calculator with the values of $T_0$, $t_n$, $T$ and $n$ set to the values appropriate
for our observations of _Plagiobothrys tenellus_ which was observed $n=2$ times in 1982 and 1998, and our
observation period bracketing these observations between 1958 and 2019. As well as $B(t)$, the Bayes factor in
favour of the null hypothesis that extinction has not occurred, we also show $PP(T)$, our prior probability of
presence and $EP(t) = 1 - PP(t)$, our prior probability of extinction which feeds into our wider analysis.

<div class="solow-container">
<link rel="stylesheet" href="../../../css/solow.css">

<div class="input-group">
    <label for="solow-t0">T₀ (Beginning of record-keeping):</label>
    <input type="number" id="solow-t0" value="1958">
</div>

<div class="input-group">
    <label for="solow-tn">tₙ (Most recent sighting):</label>
    <input type="number" id="solow-tn" value="1998">
</div>

<div class="input-group">
    <label for="solow-T">T (Current time/study endpoint):</label>
    <input type="number" id="solow-T" value="2019">
</div>

<div class="input-group">
    <label for="solow-n">n (Number of observations):</label>
    <input type="number" id="solow-n" value="2" min="1">
</div>

<div class="results" id="solow-results">
    <div class="result-item">
        <span class="result-label">Bayes factor in favour of presence B(t):</span>
        <span class="result-value" id="solow-bt">--</span>
    </div>
    <div class="result-item">
        <span class="result-label">Prior probability of presence PP(t):</span>
        <span class="result-value" id="solow-pp">--</span>
    </div>
    <div class="result-item">
        <span class="result-label">Prior probability of absence EP(t):</span>
        <span class="result-value" id="solow-ep">--</span>
    </div>
</div>
</div>

</div>

<script src="../../../js/solow.js"></script>

</div>
