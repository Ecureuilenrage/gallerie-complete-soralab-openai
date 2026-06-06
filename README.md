# Sora API Creative Lab × Paris 8 — site complet

Ce dépôt contient **l'assemblage complet** d'un projet réalisé **à deux mains**
avec **Everardo Reyes** : la vitrine du *Sora API Creative Lab* mené avec les
étudiant·es en Humanités numériques de Paris 8, **galerie embarquée comprise**.

Version live (vitrine d'origine) : https://ereyes.github.io/openai_creativelab_2026/

Le projet se compose de deux parties complémentaires, ici **réunies** :

| Partie | Rôle |
|--------|------|
| **Le site vitrine (statique)** — *Everardo Reyes* | Coquille du site : accueil, à propos, crédits, navigation, bilingue FR/EN, design system. |
| **La galerie des participant·es** — *Léon Klein* | Application React/Vite : trois vues d'exploration des projets, lecteur vidéo Drive, bilingue. Voir le dépôt source : [`gallerie-openai`](https://github.com/ereyes/openai_creativelab_2026). |

## Comment les deux parties s'assemblent

Le site est **statique** (sans outil de build). La page `galerie.html` lui est
**réservée** : la galerie React/Vite y est **embarquée** comme un composant. Elle
se monte dans `<div id="gallery-root">`, en conservant l'en-tête, le pied de page
et la navigation du site hôte.

Comme le site est statique, on n'intègre pas le code source de la galerie mais son
**build compilé prêt à servir**, versionné ici dans **[`galerie-app/`](./galerie-app/)**
(`galerie.js`, `galerie.css` et les polices). `galerie.html` ne fait que charger ce
build et lui désigner le point de montage et la cible du bouton « Retour ».

## Structure

```text
gallerie-complete-soralab-openai/
├── index.html          # Accueil : titre + accès à Galerie / À propos / Crédits
├── galerie.html        # Page Galerie : embarque le build React dans #gallery-root
├── about.html          # Page À propos enrichie à partir des sommaires de séances
├── credits.html        # Page Crédits
├── assets/
│   ├── styles.css      # Mise en page, typographie, texture film statique
│   ├── site.js         # Bascule FR/EN, texture aléatoire au chargement, année du footer
│   ├── photos/         # Photos de séances pour la page À propos
│   └── favicon.svg
├── galerie-app/        # Build React/Vite compilé de la galerie (galerie.js, galerie.css, fonts/)
├── vignettes/          # Portraits des participant·es
└── livrables/          # PDF / MP4 du projet
```

## Modifier les textes

Les textes bilingues du site vitrine sont centralisés dans `assets/site.js`,
objet `translations`.

Exemple :

```js
"home.title": "OpenAI Creative Lab : recettes, vidéos et IA générative."
```

## Mettre à jour la galerie

La galerie est livrée sous forme de **build compilé**. Pour la mettre à jour, on
recompile la galerie depuis son dépôt source (`npm run build`), puis on remplace le
contenu de [`galerie-app/`](./galerie-app/) par le nouveau build. Le détail du
montage côté site est dans [`galerie.html`](./galerie.html).

Un exemple historique de galerie chargeant ses données depuis un Google Sheet reste
consultable ici :
https://ereyes.github.io/openai_creativelab_2026/mosaic_gallery_neutral_gray.html

---

Réalisé à deux mains avec **Everardo Reyes** — *Sora API Creative Lab × Paris 8*.
