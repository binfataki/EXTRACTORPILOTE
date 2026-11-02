# Portail pilote SYDONIA

La documentation maître se trouve dans `../MANUEL_COMPLET_SYSTEME.md` dans le projet source.

Ce dossier est la version statique du portail pilote Sydonia. Il est indépendant du portail ELIMU.

## Publication GitHub Pages

1. Envoyer le contenu de ce dossier à la racine de la branche `main`.
2. Dans **Settings → Pages**, choisir **Deploy from a branch**, branche `main`, dossier `/ (root)`, puis enregistrer.
3. Ouvrir l'adresse Pages du dépôt. La page d'accueil est `index.html`.

## Configuration

L'URL Apps Script Sydonia se renseigne dans `config.js` ou dans **Configuration**. Elle est enregistrée uniquement dans ce navigateur.

Le portail pilote sert à gérer les installations et les licences. Il ne contient pas les données locales des entreprises ni le logiciel Sydonia.

Le registre est relu à l'ouverture, avec le bouton **Actualiser** et automatiquement toutes les 30 secondes lorsque la page est visible et en ligne. Une notification visuelle est affichée lorsqu'une installation passe ou reste dans l'état `EN_ATTENTE` ou `DESACTIVE`; elle est dédupliquée tant que la situation ne change pas.

## Installation sur téléphone

Le portail est une PWA mobile-first. Les appels Apps Script restent en ligne : le mode hors connexion conserve seulement l'interface du portail, sans inventer de données de licences.

## Tester avant publication

Depuis la racine du projet :

```powershell
py -m http.server 5503 --directory "GITHUB_PORTAL_PILOTE"
```

Ouvrir `http://127.0.0.1:5503/`. Vérifier l’URL Apps Script Sydonia dans **Configuration**, puis vérifier les listes, la recherche, la modification du statut et la révocation. Le logo peut être remplacé dans `assets/`.
