layout: post
title: "DiffDock: Diffusion Steps, Twists, and Turns for Molecular Docking — short explainer"
subtitle: "A simple, brief summary of what DiffDock does and why it mattered (thumbnail by Flaticon)"

cover-img: /assets/img/diffdock.png

thumbnail-img: /assets/img/diffdock-thumb.png

share-img: /assets/img/diffdock-share.jpg
tags: [DiffDock, molecular docking, diffusion models, generative models]
author: Your Name
date: 2025-10-19

DiffDock is a generative model for molecular docking. Instead of searching or regressing a single pose, it samples many candidate ligand poses by running a learned reverse-diffusion process over translation, rotation and torsion degrees of freedom. 
arXiv

How it works

A diffusion model is trained to turn random poses into realistic binding poses. 
arXiv

The model generates many poses; a small learned confidence head ranks them so you can pick the most likely ones. 
arXiv
+1

Key numbers

On a common PDBBind benchmark, DiffDock reported ~38% top-1 success (RMSD < 2.0 Å), higher than the reported baselines at the time. 
arXiv

Why people use it

It finds multiple plausible poses (helps when binding is multimodal). 
arXiv

It’s fast at inference and gives a confidence score to sort results. 
arXiv

Things to watch out for

Performance depends on training data and can drop on very different/unseen pockets. Independent follow-up work has noted cases where conventional docking workflows can be stronger if carefully run. 
arXiv
+1

For final ranking or physics-sensitive tasks, it’s common to re-score or refine DiffDock outputs with a physics-based method. 
arXiv

Try it

Code and model weights are publicly available on the authors’ GitHub repo. 
GitHub

References

G. Corso, H. Stärk, B. Jing, R. Barzilay & T. Jaakkola — DiffDock: Diffusion Steps, Twists, and Turns for Molecular Docking (paper). 
arXiv
+1

Official implementation and pretrained models — gcorso/DiffDock (GitHub). 
GitHub

Follow-up/critical analysis discussing comparisons and generalization.
