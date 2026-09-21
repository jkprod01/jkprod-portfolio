# JK Prod — Déploiement gratuit sur GitHub Pages

## Ce que fait le projet

Le site de Jefferson KONE est un front-end statique React/Vite. Il ne nécessite ni serveur payant ni base de données pour être publié sur GitHub Pages.

Le workflow `.github/workflows/deploy-pages.yml` construit et publie automatiquement le site à chaque `push` sur la branche `main` ou `master`.

## Mise en ligne en une fois

1. Créer un dépôt GitHub, par exemple `jkprod-portfolio`.
2. Envoyer tout le contenu du projet dans ce dépôt.
3. Dans GitHub, ouvrir **Settings → Pages**.
4. Dans **Build and deployment**, sélectionner **GitHub Actions**.
5. Vérifier que le fichier `.github/workflows/deploy-pages.yml` est bien présent.
6. Ouvrir l’onglet **Actions** et attendre la fin du workflow.

L’adresse gratuite sera généralement :

```text
https://VOTRE-PSEUDO.github.io/jkprod-portfolio/
```

Le workflow ajoute aussi `404.html` pour que la page reste accessible après un rechargement.

## Modifier le site

Les principaux fichiers sont :

- `client/src/pages/Home.tsx` : textes, projets, liens et structure HTML React ;
- `client/src/index.css` : couleurs, typographie, responsive et design ;
- `client/index.html` : titre, description SEO et polices ;
- `.github/workflows/deploy-pages.yml` : déploiement automatique.

Après une modification :

```bash
git add .
git commit -m "Mettre à jour le portfolio JK Prod"
git push
```

GitHub Actions republiera le site automatiquement.

## Ajouter une vidéo

Pour garder un site rapide, ne pas déposer de gros fichiers MP4 dans GitHub Pages. Héberger la vidéo sur YouTube ou Vimeo, puis renseigner son lien dans le bouton ou la fiche du projet. Une miniature légère peut être utilisée pour l’aperçu.

## Vérification locale

```bash
pnpm install
pnpm run check
pnpm run build:pages
pnpm run dev
```

Le dossier publié par le workflow est `dist/public`.
