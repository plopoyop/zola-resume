---
title: "NotFeed : un lecteur RSS sur GitHub"
date: 2021-08-28T11:40:32.885Z
extra:
  featured: true
  link: https://notcraft.alongwy.top/NotFeed/
  image: /media/notcraft.png
description: Un lecteur RSS qui s'exécute entièrement depuis votre dépôt
  GitHub.  <ul>   <li>Hébergement gratuit sur GitHub Pages. Sans publicité. Sans
  pistage tiers.</li>   <li>Aucun backend nécessaire. Le contenu est mis à jour
  via GitHub Actions.</li>   <li>Mises en page et styles personnalisables via
  une API de templating et de thèmes. Apportez simplement votre HTML et CSS.</li>   <li>Libre
  et open source. Sans pistage tiers.</li> </ul>
taxonomies:
  tags:
    - RSS
    - Rust
---
### [NotCraft::NotFeed](https://notcraft.alongwy.top/NotFeed/)

Un lecteur RSS qui s'exécute entièrement depuis votre dépôt GitHub.

* Hébergement gratuit sur [GitHub Pages](https://pages.github.com/). Sans publicité. Sans pistage tiers.
* Aucun backend nécessaire. Le contenu est mis à jour via [GitHub Actions](https://github.com/features/actions).
* Mises en page et styles personnalisables via une API de templating et de thèmes. Apportez simplement votre HTML et CSS.
* Libre et open source. Sans pistage tiers.

### Comment l'utiliser ?

#### Github Pages

1. Utilisez le [NotFeed-Template](https://github.com/NotCraft/NotFeed-Template) pour générer votre propre dépôt.
2. À la racine du dépôt, ouvrez le fichier `Config.toml`, cliquez sur le bouton « Crayon (Edit this file) » pour l'éditer.
3. Retirez `#` pour décommenter la propriété `cacheUrl`, remplacez `<github_username>` par votre nom d'utilisateur GitHub et
   remplacez `<repo>` par le nom de votre dépôt GitHub.
4. Dans `sources`, mettez à jour les éléments avec les sources que vous souhaitez suivre. Le contenu final du fichier devrait
   ressembler à ceci :

    ```toml
    # Config.toml

    site_title = "ArxivDaily"
    cache_max_days = 7
    sources = [
      "https://export.arxiv.org/rss/cs.CL"
    ]
    # proxy = "http://127.0.0.1:7890" ## Optionnel : par défaut None
    # statics_dir   = "statics"       ## Optionnel : par défaut "statics"
    # templates_dir = "includes"      ## Optionnel : par défaut "includes"
    # cache_url = "https://GITHUB_USERNAME.github.io/REPO_NAME/cache.json"
    # minify = true
    # [scripts]
    # highlight = "scripts/highlight.rhai"
    ```
5. Faites défiler la page jusqu'en bas et cliquez sur le bouton « Commit changes ».
6. Une fois la reconstruction terminée, votre flux sera disponible à l'adresse `https://<github_username>.github.io/<repo>`.

#### En local

1. Clonez le dépôt [NotFeed-Template](https://github.com/NotCraft/NotFeed-Template).
2. Modifiez le fichier `Config.toml`.
3. Exécutez `notfeed`.

   * build : `notfeed build`
   * serve : `notfeed serve --addr 127.0.0.1 --port 8080` ou simplement `notfeed serve`

#### Remerciements

* Inspiré par [osmos::feed](https://github.com/osmoscraft/osmosfeed)
