---
title: 'New package version in Bioconductor'
date: 2023-04-27
permalink: /posts/2023/04/blog-post-1/
tags:
  - Bioconductor
  - package development
  - R
  - biological networks
---

We've got the new version of the package [BioNAR](https://bioconductor.org/packages/devel/bioc/html/BioNAR.html) accepted for the Bioconductor release 3.17. The package is designed for step by step analysis biological networks with sophisticated metrics such as Perturbation Entropy or Disease-Disease separation. Package contains number of real networks as datasets: presynaptic PPI network and Barabasi's bipartite Diseasome network [Goh.t al. 2007](https://dx.doi.org/10.1073/pnas.0701361104).

The new version contains unique annotation-based pipeline evaluating clustering algorithm performances developed by [Colin McLean](https://github.com/cmclean5). 

New version allow analysis of directed graphs and add four new centrality measures specific for the directed graphs. Some annotation functions were modified to allow annotate nodes not only by its name propety but by any other arbitrary property if its value uniquely identify the node.