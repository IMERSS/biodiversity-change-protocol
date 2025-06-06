---
title: Target selection criteria
description: Honing focus on biodiversity change
categories: [Examples, Placeholders]
tags: [test, docs]
weight: 4
---

## Open-ended assessments of potential change

In order to proceed beyond an initial baseline analysis to assess possible changes in a system, we can set
useful criteria to focus our attention (and limited resources) on species that are most likely to be vulnerable.

Depending on the criteria we set, there may emerge many potential target species or populations of concern.
On the first pass, however, it is notable that this decision-making process is blind to any conservation priorities we may have,
which can bias biodiversity change assessments. We should be mindful of those biases!

{{% pageinfo %}}
"Conservation programs often prioritize species-at-risk, even while many common species may undergo the highest relative losses."
{{% /pageinfo %}}


## Criteria to consider

### Coordinate uncertainty

Geographic coordinates represent one of the most crucial pieces of information for biodiversity change assessments.

* Often we are confronted with limited locality information, which imposes constraints on representation of historical habitat patches.
* Sometimes, the information is good enough to map species occurrences to precise locations (*e.g.*, 30x30m2 grid cell)
* Sometimes, the information is good enough to specify a discrete location or habitat patch
* Sometimes, coordinates are generalized to the geometric centre (centroid) of a given area, with a wide radius of coordinate uncertainty
* Sometimes, we don't have any coordinates at all

It is exceedingly difficult if not impossible to assess the status of species or populations that lack specific locality information.
At the very least, we will want to ensure our targets have coordinates:

```
# Filter out records lacking coordinates
```

(Depending on the approach, one might want to be more strict and filter records below a certain threshold of coordinate Uncertainty)

### Provenance

Commonly, we are only concerned with the disappearance of native plants from the landscape.

```
# Filter native species
# 
```

### Historical evidence

Biological specimens are the strongest evidence we have for biodiversity change assessments.

```
# Filter voucher specimens
# 
```

### Taxonomically difficult or cryptic species

```
# Filter out graminoids
# 
```

### Number of occurrences

The number of times a species occurs in a historical record can be useful information to consider:

1) A low number of occurrences could potentially signal rarity or vulnerability. 
2) The more species occurrences, the more confidence we can have that a species was well established historically.

This prior knowledge can help to inform our assessment of the vulnerability of species to local extinction.

```
# Tabulate species record counts
#
```

Occurrence frequency is sometimes referred to as a sighting rate. This prior knowledge can be used to calculate extinction probabilities.

