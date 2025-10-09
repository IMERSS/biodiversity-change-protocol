---
title: Example 1
description: Crassula connata
math: true
weight: 3
---

## Crassula connata

For *Crassula connata*, which was seen only once in 1983 and not since, applying Solow’s formula gives a Bayes factor of 0.69—meaning the odds modestly favour absence over presence. Converting these odds into a probability yields a 41% chance that the species is still present and a corresponding 59% chance that it has been extirpated. These values serve as our prior probabilities—our best estimate of persistence or loss before incorporating any additional data or modelling.

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
