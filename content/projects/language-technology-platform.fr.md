---
title: Language Technology Platform
date: 2021-08-28T11:35:41.496Z
extra:
  featured: true
  link: https://github.com/HIT-SCIR/ltp
  image: /media/ltp.png
description: "Une plateforme open source de NLP neuronal qui prend en charge
  six tâches fondamentales du chinois : <ul>   <li>analyse lexicale (segmentation
  de mots, étiquetage morphosyntaxique et reconnaissance d'entités
  nommées)</li>   <li>analyse syntaxique (analyse en
  dépendances)</li>   <li>analyse sémantique (analyse de dépendances sémantiques
  et étiquetage en rôles sémantiques)</li> </ul>"
taxonomies:
  tags:
    - Python
    - Pytorch
    - NLP
    - Chinese
---
### Présentation
Une plateforme open source de NLP neuronal qui prend en charge six tâches fondamentales du chinois :

+ analyse lexicale (segmentation de mots, étiquetage morphosyntaxique et reconnaissance d'entités nommées)
+ analyse syntaxique (analyse en dépendances)
+ analyse sémantique (analyse de dépendances sémantiques et étiquetage en rôles sémantiques).

### Démarrage rapide

```python
from ltp import LTP

ltp = LTP()  # charge le modèle Small par défaut
seg, hidden = ltp.seg(["他叫汤姆去拿外衣。"])
pos = ltp.pos(hidden)
ner = ltp.ner(hidden)
srl = ltp.srl(hidden)
dep = ltp.dep(hidden)
sdp = ltp.sdp(hidden)
```

### Performances

|       Modèle       | CWS  | POS  | NER | SRL | DEP | SDP | Vitesse (phrases/s) |
| :-------------- | :---: | :---: | :------: | :------: | :------: | :------: | :--------: |
| LTP 4.0 (Base)   | 98.70  | 98.50  |   95.4   |   80.60   |   89.50   |   75.20   |   39.12    |
| LTP 4.0 (Base1)  | 99.22 | 98.73 |  96.39   |  79.28   |  89.57   |  76.57   |   --.--    |
| LTP 4.0 (Base2)  | 99.18 | 98.69 |  95.97   |  79.49   |  90.19   |  76.62   |   --.--    |
| LTP 4.0 (Small)  | 98.40  | 98.20  |   94.30   |   78.40   |   88.30   |   74.70   |   43.13    |
|  LTP 4.0 (Tiny)  | 96.80  | 97.10  |   91.60   |   70.90   |   83.80   |   70.10   |   53.22    |

### Citation

```latex
@article{che2020n,
  title={N-LTP: A Open-source Neural Chinese Language Technology Platform with Pretrained Models},
  author={Che, Wanxiang and Feng, Yunlong and Qin, Libo and Liu, Ting},
  journal={arXiv preprint arXiv:2009.11616},
  year={2020}
}
```
