---
title: Data synthesis
description: Dealing with messy data
categories: [Examples, Placeholders]
tags: [test, docs]
weight: 2
---

## Combination of heterogeneous data in baseline analyses

Statistical approaches to modeling biodiversity change are often paralyzed by limitations and deficiencies inherent
in biodiversity data—especially when historical and contemporary data are combined from multiple sources.

* Data are commonly unstructured, or heterogeneous, lacking consistent attributes or metadata
* Data are often biased toward positive detections (lacking absence information)
* Data may be collected in ways that violate the assumptions of statistical models
* Georeferencing is often generalized based on vague locality information
* Data may be sparse, with few or perhaps only singleton records to vouch for historical populations, especially at local scales

## Baseline analyses offer a practical approach

A practical approach to this difficult situation is to forego any advanced modeling practices *ab initio*
and begin instead with a simple baseline analysis of historical *vs* contemporary sources of biodiversity data.
This depends on normalization of species occurrence data to support the comparison of historical and contemporary species records.

{{% pageinfo %}}
Normalization of biodiversity data is a thorny enough problem in its own right and not treated here. For this
tutorial we assume that names are aligned and any synonymy is resolved between the data being compared.
{{% /pageinfo %}}

* Best practices are to adhere to the Darwin Core standard for species occurrence data.
* Different communities may prefer to adhere to different taxonomic databases. Any taxonomic standard can be observed, as 
long as it results in consistent mapping of taxa between datasets.

```
### Integrate biodiversity data and summarize 

```