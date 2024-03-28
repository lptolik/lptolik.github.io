---
title: 'Artificial Intelligence or Stochastic Parrot'
date: 2024-03-28
permalink: /posts/2024/03/blog-post-1/
tags:
  - AI
  - biological networks
  - diagram
---

Recent progress on development of generative AI systems cause a discussion of the area of their applicability. Recent paper 
	Lisa Messeri, M. J. Crockett (2024) &quot;Artificial intelligence and illusions of understanding in scientific research&quot; <i>Nature</i> [10.1038/s41586-024-07146-0](http://dx.doi.org/10.1038/s41586-024-07146-0)

describes some risks that generative AI poses on research community if used blindly. 

The main mode discussed in relation to generative AI is text-to-text, like chatBots. We have played with text-to-image to see if we can get any reasonable result in diagram generation. We asked Dall-E image generator to draw "A detailed and educational illustration of the glycolytic pathway, showcasing each step in a clear and organized manner", and what we've got:

![](/images/dalle-1.png)

Very nice-looking picture, but absolutely meaningless. First of all it takes style from signaling pathway posters, like ones taken from  [here](https://ruo.mbl.co.jp/bio/e/literature/pathways/nf-kappab.html):![](https://ruo.mbl.co.jp/bio/e/literature/pathways/images/NF-KappaB-Pathway.jpg)

Then, no name without mistake, and the final one the diagram is meaningless. Glycolysis, as we all know, takes place in cytosol, there is no need to draw mitochondrial lumen despite how beautiful picture is, and neither names nor connections within lumen have no meaning.

We have tried one more time, now Dall-E respond:
	I've created an updated illustration that incorporates the real names and structural formulas of compounds involved in both the glycolytic pathway and the TCA cycle. This version emphasizes scientific accuracy, showcasing each compound's role and the enzymes responsible for their transformation.

and draw the picture

![](/images/dalle-2.png) 

This time we see the cycle, even two of them. On top that cycle, for some reason, alien DNA is drawn. It is alien, no doubts, as normal Earth-evolved DNA have only two strains, not three. Again no meaningful names on the picture, however some could be guessed. But they are placed randomly, for example fumarate is not a cyclic hexose, as shown on the picture.

And the final funny note: glycolysis with smiles:
![](/images/dalle-3.png) 