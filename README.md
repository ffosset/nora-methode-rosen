# Nora Römer — Méthode Rosen

Site vitrine de Nora Römer, praticienne de la Méthode Rosen à Forest (Bruxelles).

En ligne : https://noraromer.be/

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

## Modifier le site depuis GitHub

Pas besoin d'installer quoi que ce soit : tout se fait sur github.com, dans le navigateur. Chaque modification enregistrée est en ligne en une minute ou deux.

Il faut un compte GitHub et avoir été ajouté·e comme collaborateur·rice du repo (Settings → Collaborators).

### Changer un texte

1. Ouvrir `index.html` sur github.com et cliquer sur l'icône crayon.
2. Chercher la phrase avec Ctrl+F (Cmd+F sur Mac) et la modifier.
3. Cliquer sur **Commit changes** : la modification est enregistrée et publiée.

Le texte se trouve entre des balises HTML, comme `<p>…</p>`. Ne changer que les mots, sans toucher aux balises.

### Remplacer une photo

Le plus simple est de garder le même nom de fichier.

1. Aller dans le dossier `images/`, puis **Add file → Upload files**.
2. Envoyer la nouvelle photo en deux versions, `.jpg` et `.webp`, avec exactement les mêmes noms que l'ancienne (par exemple `nora.jpg` et `nora.webp`). GitHub remplace les anciens fichiers.

⚠️ Il faut bien remplacer les deux fichiers. La plupart des navigateurs affichent la version `.webp` : si seul le `.jpg` change, les visiteurs verront toujours l'ancienne photo. Pour créer le `.webp`, un convertisseur en ligne gratuit comme [squoosh.app](https://squoosh.app) fait l'affaire.

Si la nouvelle photo n'a pas la même forme (paysage au lieu de portrait, par exemple), il faut aussi mettre à jour `width` et `height` dans le HTML. Pour ajouter une nouvelle photo plutôt qu'en remplacer une, voir plus bas.

### Modifications plus importantes

Appuyer sur la touche `.` depuis la page du repo ouvre github.dev, un éditeur complet dans le navigateur. On peut y modifier plusieurs fichiers et tout enregistrer en une seule fois.

## Aperçu en local

```bash
python3 -m http.server 8000
```

Puis ouvrir http://localhost:8000.

Si le site est aussi modifié depuis GitHub, toujours faire `git pull` avant de travailler en local, pour éviter les conflits.

## Ajouter ou remplacer une photo

1. Exporter la photo en `.jpg` (1280 px sur le grand côté) dans `images/`.
2. En créer une version `.webp` du même nom, par exemple avec `cwebp -q 80 photo.jpg -o photo.webp`.
3. L'intégrer avec un `<picture>` (webp + repli jpg) en indiquant `width`, `height` et un `alt` descriptif, comme les photos existantes de `index.html`.
4. Si la photo doit apparaître dans Google Images, l'ajouter aussi à `sitemap.xml`.
