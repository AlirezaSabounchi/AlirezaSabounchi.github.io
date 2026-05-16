---
layout: post
title: "Transformers in Molecular Property Prediction"
subtitle: "Harnessing Transformer Architectures for Enhanced Molecular Analysis (thumbnail by AI Emoji Generator)"
# cover-img: /assets/img/transformers_molecular.png
thumbnail-img: /assets/img/transformers_molecular_thumb.png
tags: [transformers, molecular property prediction, deep learning, cheminformatics]
author: Ali Reza Sabounchi
---
Since we cannot seem to avoid hearing about transformers (ChatGPT specifically), we might as well acknowledge their impact on, well, everything. The advent of transformer architectures has certainly revolutionized various fields in natural language processing and computer vision, among all other academic majors to ever exist. Recently, their application has extended into cheminformatics, particularly in predicting molecular properties (I might have something to do with this, as I used ChemBERTa in my work. more on that later). By treating molecular structures as sequences or even graphs, transformers can learn intricate patterns that govern molecular behavior.

### An (unnecessary) Introduction to Transformers

Transformers, introduced in the not-so-easy-to-follow paper ["Attention is All You Need"](https://arxiv.org/abs/1706.03762), utilize self-attention mechanisms to weigh the significance of different input elements. This allows the model to capture long-range dependencies and complex relationships within data, making it highly effective for sequential information. To offset this advantage, it is note-worthy that they also need exponentially larger datasets compared to simpler models (e.g., linear regression, SVM,...). This could explain why every company out there is looking for a way to obtain and/or sell (your) data.

### Application in Molecular Property Prediction

In molecular property prediction (which I like), the goal is to determine attributes such as toxicity, solubility, or biological activity of compounds (similar to MoleculeNet). Traditional methods often rely on handcrafted features, which can be limiting (BUT can be equally as accurate, as per my thesis work's results). Transformers offer a data-driven approach by learning representations directly from raw molecular data. For instance, by representing molecules as SMILES strings (a textual (1D) representation of chemical structures), transformers can process these sequences to predict properties. Alternatively, graph-based transformers interpret molecules as graphs, where atoms are nodes, and bonds are edges, capturing the spatial and relational information inherent in chemical structures. This second approach usually yields more accurate results compared to simpler GNNs like convolutional GNNs).

### Advantages(?) Over Traditional Methods

- **Feature Learning**: Transformers automatically learn relevant (yet, sometimes chemically meaningless) features from data, eliminating the need for manual feature engineering. I pesonally do not like the idea of disregarding the ever-so-uselful physiochemical features, because no architecure is intelligent enough to re-discover all of them from limited data.
- **Scalability**: They can handle large datasets and complex molecules, making them suitable for high-throughput screening.
- **Accuracy**: Studies have shown that transformer-based models often outperform traditional machine learning methods in predicting molecular properties. But are they outperfoming them in real-life experiments too or are they just overfitting a specific dataset to publish a paper?

### Challenges and Possible Future Directions

Despite their advantages(?), challenges remain in applying transformers to molecular property prediction. High-quality labeled data is limited in chemistry, which can hinder model training.Plus, understanding the decision-making process of transformers is too complex, which gives rise to more challenges in fields where explainability is crucial (e.g., drug design). Future research should logically aim to address these challenges by developing methods for data augmentation (I did come up with a great augmentation method for chemical data ;D), transfer learning (10/10, recommend), and improving model interpretability.

### Conclusion

Transformers hold significant promise in advancing molecular property prediction (hopefully not industry hype), offering a powerful tool for drug discovery and development. As research progresses, we can anticipate more robust and interpretable models that will further integrate AI into cheminformatics.

