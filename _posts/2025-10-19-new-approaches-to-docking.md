---
layout: post
title: "DiffDock: Short & Sweet"
subtitle: "A simple, brief summary of what DiffDock does (thumbnail from the original paper)"
# cover-img: /assets/img/diffdock.png
thumbnail-img: /assets/img/DiffDock-1.png
# share-img: /assets/img/diffdock-share.jpg
tags: [DiffDock, molecular docking, diffusion models, generative models]
author: Alireza Sabounchi
date: 2025-10-19
---
The other day I came across this interesting paper that incorporated diffusion models with molecular docking, which I find very intriguing, as this approach is usually reserved for image-based models. DiffDock is a generative model for molecular docking, that instead of searching or regressing a single pose, samples many candidate ligand poses by running a learned reverse-diffusion process over translation, rotation and torsion degrees of freedom. 

How it works:

A diffusion model is trained to turn random poses into realistic binding poses. The model generates many poses; a small learned confidence head ranks them so you can pick the most likely ones. 

On a common PDBBind benchmark, DiffDock reported ~38% top-1 success (RMSD < 2.0 Å), higher than the reported baselines at the time. This may not be that impressive, however, I find that it is a very promising initiative that has a lot of potential.
It also finds multiple plausible poses (helps when binding is multimodal). It’s fast at inference and gives a confidence score to sort results. 


Something to watch out for!

Performance depends on training data and can drop on very different/unseen pockets. Independent follow-up work has noted cases where conventional docking workflows can be stronger if carefully run. 


For final ranking or physics-sensitive tasks, it’s common to re-score or refine DiffDock outputs with a physics-based method. 


Try it for yourself! Code and model weights are publicly available on the authors’ GitHub repo. I will definitely try to figure it out myself.

References:

G. Corso, H. Stärk, B. Jing, R. Barzilay & T. Jaakkola — DiffDock: Diffusion Steps, Twists, and Turns for Molecular Docking (paper)