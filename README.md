# Nora Römer — Méthode Rosen

Site vitrine de Nora Römer, praticienne de la Méthode Rosen à Forest (Bruxelles).

En ligne : https://ffosset.github.io/nora-methode-rosen/

## Structure

```
index.html              page principale (CSS et JS intégrés)
mentions-legales.html
404.html                page d'erreur GitHub Pages
images/                 photos (.jpg + .webp) et logo
favicon-32.png          icônes : restent à la racine
apple-touch-icon.png
robots.txt, sitemap.xml SEO
.nojekyll               désactive Jekyll sur GitHub Pages
```

Pas de build : les fichiers sont servis tels quels.

## Déploiement

GitHub Pages, depuis la branche `main`. Chaque push sur `main` met le site à jour en une minute ou deux.

## Aperçu en local

```bash
python3 -m http.server 8000
```

Puis ouvrir http://localhost:8000.

## Ajouter ou remplacer une photo

1. Exporter la photo en `.jpg` (1280 px sur le grand côté) dans `images/`.
2. En créer une version `.webp` du même nom, par exemple avec `cwebp -q 80 photo.jpg -o photo.webp`.
3. L'intégrer avec un `<picture>` (webp + repli jpg) en indiquant `width`, `height` et un `alt` descriptif, comme les photos existantes de `index.html`.
4. Si la photo doit apparaître dans Google Images, l'ajouter aussi à `sitemap.xml`.
