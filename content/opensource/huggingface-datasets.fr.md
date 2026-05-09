---
title: Huggingface/datasets
extra:
  featured: true
  link: https://github.com/huggingface/datasets
  image: /media/huggingface_logo.svg
description: 🤗 Le plus grand hub de jeux de données prêts à l'emploi pour les
  modèles ML, avec des outils rapides, simples et efficaces de manipulation de données
taxonomies:
  tags:
    - NLP
    - Datasets
---
🤗 Datasets est une bibliothèque légère qui propose deux fonctionnalités principales :

des chargeurs de données en une ligne pour de nombreux jeux de données publics :

+ des one-liners pour télécharger et prétraiter n'importe quel jeu de données public majeur (dans 467 langues et dialectes !) disponible sur le HuggingFace Datasets Hub. Avec une simple commande comme `squad_dataset = load_dataset("squad")`, obtenez n'importe lequel de ces jeux de données prêt à être utilisé dans un dataloader pour l'entraînement ou l'évaluation d'un modèle ML (Numpy/Pandas/PyTorch/TensorFlow/JAX).
+ un prétraitement de données efficace : prétraitement simple, rapide et reproductible, aussi bien pour les jeux de données publics que pour vos propres jeux de données locaux au format CSV/JSON/texte. Avec des commandes simples comme `tokenized_dataset = dataset.map(tokenize_example)`, préparez efficacement le jeu de données pour l'inspection, l'évaluation et l'entraînement de modèles ML.
