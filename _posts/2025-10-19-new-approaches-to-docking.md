---
layout: post
title: "DiffDock: Diffusion Steps, Twists, and Turns for Molecular Docking — short explainer"
subtitle: "A simple, brief summary of what DiffDock does and why it mattered (thumbnail by Flaticon)"
# cover-img: /assets/img/diffdock.png
thumbnail-img: /assets/img/diffdock-thumb.png
# share-img: /assets/img/diffdock-share.jpg
tags: [DiffDock, molecular docking, diffusion models, generative models]
author: Alireza Sabounchi
date: 2025-10-19
---
DiffDock is a generative model for molecular docking. Instead of searching or regressing a single pose, it samples many candidate ligand poses by running a learned reverse-diffusion process over translation, rotation and torsion degrees of freedom. 

How it works:
A diffusion model is trained to turn random poses into realistic binding poses. 
The model generates many poses; a small learned confidence head ranks them so you can pick the most likely ones. 


Key numbers:
On a common PDBBind benchmark, DiffDock reported ~38% top-1 success (RMSD < 2.0 Å), higher than the reported baselines at the time. 


Why people use it:
It finds multiple plausible poses (helps when binding is multimodal). 
It’s fast at inference and gives a confidence score to sort results. 


Things to watch out for:
Performance depends on training data and can drop on very different/unseen pockets. Independent follow-up work has noted cases where conventional docking workflows can be stronger if carefully run. 


For final ranking or physics-sensitive tasks, it’s common to re-score or refine DiffDock outputs with a physics-based method. 


Try it! Code and model weights are publicly available on the authors’ GitHub repo. 
GitHub

References:
G. Corso, H. Stärk, B. Jing, R. Barzilay & T. Jaakkola — DiffDock: Diffusion Steps, Twists, and Turns for Molecular Docking (paper)