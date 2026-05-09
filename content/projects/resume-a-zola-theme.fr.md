---
title: "Resume : un thème Zola"
date: 2021-09-03T13:30:54.712Z
description: "Resume : un thème Zola"
extra:
  link: https://github.com/AlongWY/zola-resume
  image: /media/open-source.png
---
# Zola Resume

## Démarrage rapide

```bash
git clone git@github.com:alongwy/zola-resume.git
cd zola-resume
zola serve
# ouvrir http://127.0.0.1:1111/
```

**Mettre à jour le thème par la suite peut s'avérer fastidieux avec cette méthode.**

## Installation

### Étape 1 : initialiser le site

```bash
zola init mysite
```

### Étape 2 : installer zola-resume

Installez le thème dans le dossier `themes` :

```bash
cd mysite/themes
git clone git@github.com:alongwy/zola-resume.git
```

Ou en tant que submodule :

```bash
cd mysite
git init  # à ignorer si votre projet est déjà un dépôt git
git submodule add git@github.com:alongwy/zola-resume.git themes/zola-resume
```

### Étape 3 : configurer le site

Activez le thème dans le fichier `config.toml` :

```toml
theme = "zola-resume"
```

Ou copiez directement `config.toml.example` à la racine :

```bash
cp themes/zola-resume/config.toml.example config.toml
```

### Étape 4 : ajouter ou modifier le contenu

Copiez ensuite :

```
cp -r themes/zola-resume/data .
cp -r themes/zola-resume/content .
```

Vous pouvez modifier ou ajouter du contenu dans `content/blog`, `content/projects`, etc. Attention à ne pas supprimer les fichiers `_index.md`.

### Étape 5 : lancer le projet

Lancez la commande suivante pour visualiser le résultat :

```
zola serve
```

Ouvrez http://127.0.0.1:1111 pour voir le rendu.

### Étape 6 : build automatique

Copiez le fichier de configuration GitHub Actions :

```bash
mkdir -p .github/workflows
cp themes/zola-resume/build.yml .github/workflows/build.yml
```

## Configurer le CMS

### Étape 1 : modifier le fichier de configuration

Copiez le fichier de configuration du CMS :

```bash
cp themes/zola-resume/static/admin/config.yml static/admin/config.yml
```

Et modifiez la section suivante :

```yaml
# static/admin/config.yml

backend:
  name: github
  repo: USERNAME/REPO             # <-- à modifier
  branch: BRANCH                  # <-- à modifier
  cms_label_prefix: netlify-cms/
  site_domain: DOMAIN.netlify.com # gardez cette valeur, elle servira plus tard
```

## Configurer l'authentification de l'admin

Créez d'abord un compte sur [Netlify](https://netlify.com) et configurez le dépôt — le build automatique échouera, ce n'est pas grave.

Dans les `Settings` du site, sous `Build & deploy`, désactivez l'option `active` des `Build settings` pour ne pas consommer le quota de build automatique de Netlify.

Toujours dans `Settings`, allez dans `Access control` puis `OAuth`, cliquez sur `Install provider` et installez GitHub. Pour configurer l'app GitHub, voyez [cette documentation](https://docs.netlify.com/visitor-access/oauth-provider-tokens/).

Enfin, dans `Settings` → `Custom domains`, ajoutez `YOURNAME.github.io` (ignorez l'avertissement) et notez le `Default subdomain` affiché plus haut, à reporter dans `static/admin/config.yml` sous `backend.site_domain`.


### Page « À propos »
Modifiez `contents/_index.md` pour changer le contenu de la page d'accueil.

### Autres fichiers

- [data/certifications.json](https://github.com/AlongWY/zola-resume/blob/main/data/certifications.json)
- [data/social.json](https://github.com/AlongWY/zola-resume/blob/main/data/social.json)
- [data/skills.json](https://github.com/AlongWY/zola-resume/blob/main/data/skills.json)
- [data/experience.json](https://github.com/AlongWY/zola-resume/blob/main/data/experience.json)
- [data/education.json](https://github.com/AlongWY/zola-resume/blob/main/data/education.json)
