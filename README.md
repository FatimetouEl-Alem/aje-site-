# Agence judiciaire de l’État — Site web

Site statique (HTML, CSS, JavaScript) sans étape de compilation. Le design est identique à la maquette d’origine `aje-accueil.html` : seul le découpage en fichiers a changé.

## Structure

```
index.html                     Page unique du site (point d’entrée)
assets/css/style.css           Toutes les feuilles de style
assets/js/main.js              Contenu FR/AR, navigation et pages
assets/img/logo.png            Sceau de l’Agence
assets/img/favicon.png         Icône du site
assets/img/couvertures/        Couvertures des publications (FR et AR)
assets/img/actualites/         Photos des actualités
```

## Pages

Le site est une application d’une seule page : toutes les pages sont générées par `assets/js/main.js` et accessibles par adresse `#/…` :

`#/accueil`, `#/agence`, `#/mot-agent`, `#/juridique`, `#/guide`, `#/amiable`, `#/jurisprudence`, `#/publications`, `#/actualites`, `#/connexion`, `#/contact`, `#/dossier`, `#/recherche`, `#/mentions`, `#/confidentialite`, `#/accessibilite`, `#/identite`.

Version arabe : ajouter `?lang=ar` à l’adresse (ex. `index.html?lang=ar#/accueil`) ou utiliser le bouton de langue.

## Tester en local

```bash
python3 -m http.server 8000
# puis ouvrir http://localhost:8000
```

## Mettre dans Git

```bash
git init
git add .
git commit -m "Site de l’Agence judiciaire de l’État"
git branch -M main
git remote add origin <URL_DU_DEPOT>
git push -u origin main
```

## Déploiement

Copier le contenu du dossier à la racine de n’importe quel hébergement statique (Apache, Nginx, GitHub Pages, Netlify, Vercel…). Aucune configuration de serveur n’est nécessaire, car la navigation passe par `#/`.

Les polices (Source Serif 4, Inter, Archivo, IBM Plex Mono, Cairo) sont chargées depuis Google Fonts.

## Remplacer les images

Les couvertures et photos sont des visuels provisoires. Pour les remplacer, garder le même nom de fichier dans `assets/img/…`, ou modifier les tableaux `COVERS` et `PRESS_PHOTOS` dans `assets/js/main.js`.
