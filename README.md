# Guinea Offensive Security - Site Jekyll

Site web statique pour Guinea Offensive Security, construit avec Jekyll et TailwindCSS.

## Prérequis

- Ruby 2.7.0 ou supérieur
- Bundler
- Node.js (pour TailwindCSS)

## Installation

1. Clonez le dépôt :
```bash
git clone https://github.com/votre-username/jekyll-guinea-offsec.git
cd jekyll-guinea-offsec
```

2. Installez les dépendances Ruby :
```bash
bundle install
```

3. Installez les dépendances Node.js :
```bash
npm install
```

## Développement local

Pour lancer le serveur de développement :

```bash
bundle exec jekyll serve
```

Le site sera accessible à l'adresse : `http://localhost:4000`

## Structure du projet

```
jekyll-guinea-offsec/
├── _config.yml           # Configuration principale
├── _data/               # Données statiques
│   ├── team.yml         # Membres de l'équipe
│   ├── sponsors.yml     # Sponsors
│   └── social.yml       # Réseaux sociaux
├── _includes/           # Composants réutilisables
├── _layouts/            # Templates de pages
├── _posts/              # Articles de blog
├── _sass/               # Styles SCSS
├── assets/              # Ressources statiques
├── blog/                # Page blog
├── about/               # Page about
├── join/                # Page join
├── sponsors/            # Page sponsors
└── 404.html             # Page 404
```

## Ajouter du contenu

### Articles de blog

1. Créez un nouveau fichier dans `_posts/` avec le format : `YYYY-MM-DD-titre.md`
2. Utilisez le front matter suivant :
```yaml
---
layout: post
title: "Titre de l'article"
date: YYYY-MM-DD
image: /assets/images/posts/image.jpg
tags: [tag1, tag2]
excerpt: "Extrait de l'article..."
---
```

### Membres de l'équipe

1. Modifiez le fichier `_data/team.yml`
2. Ajoutez un nouveau membre :
```yaml
- name: "Nom du membre"
  role: "Rôle"
  image: "/assets/images/team/membre.jpg"
  bio: "Biographie"
  social:
    twitter: "@handle"
    github: "username"
    linkedin: "profile"
```

### Sponsors

1. Modifiez le fichier `_data/sponsors.yml`
2. Ajoutez un nouveau sponsor :
```yaml
- name: "Nom du sponsor"
  logo: "/assets/images/sponsors/logo.png"
  url: "https://sponsor.com"
  tier: "gold" # gold, silver, bronze
```

## Déploiement

### GitHub Pages

1. Créez un dépôt GitHub
2. Activez GitHub Pages dans les paramètres du dépôt
3. Configurez la branche `gh-pages` ou `main`
4. Le site sera automatiquement déployé

## Personnalisation

### Styles

- Les styles principaux sont dans `_sass/custom.scss`
- TailwindCSS est utilisé via CDN
- La palette de couleurs peut être modifiée dans le fichier de configuration

### Configuration

Modifiez `_config.yml` pour :
- Changer le titre et la description du site
- Configurer les plugins
- Modifier les paramètres de pagination
- Ajouter des variables globales

## Licence

Ce projet est sous licence MIT. Voir le fichier `LICENSE` pour plus de détails. 