---
title: "N-LTP : une plateforme open source de NLP neuronal pour le chinois avec
  modèles pré-entraînés"
date: 2021-08-28T11:00:37.434Z
extra:
  featured: true
  link: https://arxiv.org/abs/2009.11616
  bibtex: /media/nltp.bib
  pubtype: Article
  image: /media/acl-logo.svg

description: "Une plateforme open source de NLP neuronal qui prend en charge
  six tâches fondamentales du chinois : <ul>   <li>analyse lexicale (segmentation
  de mots, étiquetage morphosyntaxique et reconnaissance d'entités
  nommées)</li>   <li>analyse syntaxique (analyse en
  dépendances)</li>   <li>analyse sémantique (analyse de dépendances sémantiques
  et étiquetage en rôles sémantiques)</li> </ul>"
taxonomies:
  tags:
    - EMNLP
    - Python
    - Pytorch
    - Demo
    - Chinese
---
Une plateforme open source de NLP neuronal qui prend en charge six tâches fondamentales du chinois :

+ analyse lexicale (segmentation de mots, étiquetage morphosyntaxique et reconnaissance d'entités nommées)
+ analyse syntaxique (analyse en dépendances)
+ analyse sémantique (analyse de dépendances sémantiques et étiquetage en rôles sémantiques).

Contrairement aux outils existants à l'état de l'art, comme Stanza, qui adoptent un modèle indépendant pour chaque tâche, N-LTP repose sur un framework multi-tâches utilisant un modèle pré-entraîné partagé, ce qui permet de capturer les connaissances communes entre les tâches chinoises liées.

De plus, la distillation de connaissances — où le modèle mono-tâche enseigne au modèle multi-tâches — est introduite pour aider le modèle multi-tâches à dépasser son enseignant mono-tâche.

Enfin, nous fournissons un ensemble d'API faciles d'utilisation et un outil de visualisation pour faciliter la prise en main et l'inspection des résultats. À notre connaissance, c'est le premier outil prenant en charge ces six tâches fondamentales du NLP chinois.
