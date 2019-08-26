---
layout: post
title: Jacob Beel
post-title: The Problems with Mode Collapse
excerpt: My first experiments led to mode collapse, what steps can we take to fix that problem?
---

Just putting together a simple, 2-layer GAN led to some interesting, but ultimately disappointing results. The system did learn to generate DND spells (at least, the numerically-representable portion of DND spells), but I ran into an issue commonly known as [mode collapse](https://aiden.nibali.org/blog/2017-01-18-mode-collapse-gans/). Obviously, DND spells are multimodal in a few ways, so having a single, strange, necromancy counterspell that hits in a 60ft cone be every single result is unrealistic and (more importantly) underwhelming.

I chose to tackle this problem by using an unrolled GAN (code can be found [here](https://colab.research.google.com/drive/1rfCHlu1WMYFO2uy-LWQ50nVVsOD8wb3Z), go ahead and give it a run to see the results that I'm talking about). And then we see some very interesting and compelling results coming out of the GAN. Apart from a couple of bad duration fields, presumably a problem with the dataset, spells are relatively diverse and indicate that I'm heading in the right direction. Expanding on this, experimenting with different hyperparemeters, and doing some statistical analysis will comprise the next steps of this project.