---
title: 'New package in Bioconductor'
date: 2022-11-01
permalink: /posts/2022/11/blog-post-1/
tags:
  - Bioconductor
  - package development
  - R
  - biological networks
---

We've got the new package [BioNAR](https://bioconductor.org/packages/devel/bioc/html/BioNAR.html) accepted for the Bioconductor release 3.16. The package is designed for step by step analysis biological networks with sophisticated metrics such as Perturbation Entropy or Disease-Disease separation. Package contains number of real networks as datasets: presynaptic PPI network and Barabasi's bipartite Diseasome network [Goh.t al. 2007](https://dx.doi.org/10.1073/pnas.0701361104].

Another two packages [synaptome.db](https://bioconductor.org/packages/3.16/data/annotation/html/synaptome.db.html) and [synaptome.data](https://bioconductor.org/packages/3.16/data/annotation/html/synaptome.data.html) were updated. More synaptic dataset and new information about mutations were added to the database underneath both of them. The synaptome.db now able to filter proteins by number of citing datasets, so user could build his own subset of proteins for further analysis.