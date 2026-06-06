# Sora API Creative Lab × Paris 8 — vitrine

Prototype bilingue pour la vitrine du Sora API Creative Lab avec les étudiant·es en Humanités numériques de Paris 8.

Version live : https://ereyes.github.io/openai_creativelab_2026/  

## Structure

```text
openai-creative-lab-vitrine/
├── index.html          # Accueil minimal : titre + accès à Galerie / À propos / Crédits
├── galerie.html        # Point d’accroche temporaire pour la galerie de Léon
├── about.html          # Page À propos enrichie à partir des sommaires de séances
├── credits.html        # Page Crédits
├── assets/
│   ├── styles.css      # Mise en page, typographie, texture film statique
│   ├── site.js         # Bascule FR/EN, texture aléatoire au chargement, année du footer
│   ├── photos/         # Photos de séances pour la page À propos
│   └── favicon.svg
└── livrables/          # Emplacement futur pour PDF / MP4
```


## Modifier les textes

Les textes bilingues sont centralisés dans `assets/site.js`, objet `translations`.

Exemple :

```js
"home.title": "OpenAI Creative Lab : recettes, vidéos et IA générative."
```

## Intégrer la future galerie

`galerie.html` est volontairement minimal. Léon peut :

1. remplacer directement son contenu ;
2. garder le header/footer et injecter plusieurs vues de navigation ;
3. utiliser les données dans le tableau Google Sheet

Un exemple de galerie qui charge les données depuis un Google Sheet est ici :   
https://ereyes.github.io/openai_creativelab_2026/mosaic_gallery_neutral_gray.html   





"# gallerie-complete-soralab-openai" 
