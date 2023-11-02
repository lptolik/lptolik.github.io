---
title: 'Bioconductor'
date: 2023-10-28
permalink: /posts/2023/10/blog-post-2/
tags:
  - Bioconductor
  - package development
  - R
  - biological networks
  - release
---

The new version (1.4) of the  [BioNAR](https://bioconductor.org/packages/3.18/bioc/html/BioNAR.html) 
package is released. In this version we add the number of important features:

## Edge weights
From version 1.3.5 the edge weights can be taken into account in clustering and 
centrality measure calculations by `weight` parameter or graph edge attribute. 
The value of `weight` parameter must be a positive numeric vector, `NULL` or `NA`. 
If it is `NULL` and the input graph has a ‘weight’ edge attribute, then that 
attribute will be used. If `NULL` and no such
attribute is present, then the edges will have equal weights. Set
this to `NA` if the graph was a `weight` edge attribute, but you don't
want to use it for community detection. A larger edge weight means a
stronger connection for this function. The weights value is ignored
for the `spectral` clustering algorithm.

There is one important nuance that have to be taken into account: 
different algorithms treat weights differently. For example, in the *betweenness* 
calculations edge weight is treated as edge length: the higher the weight the longer the 
distance between nodes and the lower the probability that this edge will be part of the 
shortest path. At the same time, in the *Page Rank* "an edge with a larger weight is more 
likely to be selected by the surfer", which infer the opposite meaning.

Taking into account that all implemented clustering algorithms treat edge weight as an 
interaction strength measure, i.e. in the same way as *Page Rank* algorithm we use this 
meaning as the default. So for all versions of distance-based centrality measure 
calculations such as *betweenness* (`BET`, `dBET`) and shortest path statistics (`mnSP` 
and `sdSP`) we calculate the distance as 

$$ distance = \frac{1}{weight}$$

for consistency.

## DYNAMO perturbation pattern calculations

In 2018 Santolini and Barabasi publish a 
[paper](https://pnas.org/doi/full/10.1073/pnas.1720589115) in which they show that 
topology of interaction graph can up to some extent reproduce sensitivity patterns of 
underlying dynamical system. They call their algorithm DYNAMO (DYNamics-Agnostic Network 
MOdels). For us that algorithm is interesting as it allow negative edge weights to 
represent inhibition interactions within the network. We rework their original code from 
[https://github.com/msantolini/dynamo/] to use sparse matrices, which is necessary to work 
with large graphs. 

## Decoupling from synaptome.db and synaptome.data packages

In the process of refactoring the code for execution in a parallel manner in HPC 
environment we realise that dependency from 
[synaptome.db](https://bioconductor.org/packages/3.18/data/annotation/html/synaptome.db.html) 
and because of it from 
[synaptome.data](https://bioconductor.org/packages/3.18/data/annotation/html/synaptome.data.html) 
makes initialisation of the computing environment extremely time consuming. Taking into 
account that the only reason for these dependencies is the construction of PPI networks 
via querying synaptome database, we decided that the dependency should be reversed: 
network creation should be created within [synaptome.db](https://bioconductor.org/packages/3.18/data/annotation/html/synaptome.db.html) 
package with the help of BioNAR functionality. So from version 1.4 BioNAR do not use any 
code from the [synaptome.db](https://bioconductor.org/packages/3.18/data/annotation/html/synaptome.db.html).

