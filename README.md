![Stade des Maths](illustration.png)

# Stade des Maths

Application d'entraînement en mathématiques et en géométrie pour les élèves de **6e**, aux couleurs du **foot** et du **rugby**.

- 21 thèmes du programme de 6e (cycle 3), répartis en 4 domaines : Nombres et calculs, Grandeurs et mesures, Espace et géométrie, Données et proportionnalité.
- 100 exercices par thème (facile, moyen, difficile), soit 2 100 exercices, chacun avec un **corrigé détaillé**.
- L'élève choisit son sport (foot ou rugby) et gagne des étoiles, des points, des catégories (U11 → Légende) et des trophées. Il peut aussi jouer un « match éclair » ou une « séance de tirs au but » de 10 questions.
- Une fois installée sur le téléphone, l'application fonctionne **sans connexion internet**. La progression est enregistrée sur le téléphone.

## Mettre l'application en ligne avec GitHub Pages

1. Créer un compte sur [github.com](https://github.com), puis un nouveau dépôt **public** (par exemple `stade-des-maths`).
2. Dans le dépôt, cliquer sur **Add file → Upload files** et glisser **tout le contenu de ce dossier** (les fichiers `index.html`, `manifest.webmanifest`, `sw.js`, les images, `.nojekyll` et le dossier `sources`). Valider avec **Commit changes**.
3. Aller dans **Settings → Pages**. Sous « Build and deployment », choisir **Deploy from a branch**, la branche **main**, le dossier **/ (root)**, puis **Save**.
4. Après une ou deux minutes, l'adresse du site apparaît en haut de cette page, sous la forme `https://votre-pseudo.github.io/stade-des-maths/`.

## Installer l'application sur un smartphone

- **Android (Chrome)** : ouvrir l'adresse du site, puis toucher le menu **⋮** et choisir **Installer l'application** (ou **Ajouter à l'écran d'accueil**).
- **iPhone (Safari)** : ouvrir l'adresse du site, toucher le bouton **Partager**, puis **Sur l'écran d'accueil**.

L'icône « 6e » apparaît alors sur l'écran d'accueil, comme une vraie application.

## Contenu du dossier

| Fichier | Rôle |
|---|---|
| `index.html` | l'application complète (exercices, corrigés, interface) |
| `manifest.webmanifest` | nom, couleurs et icônes pour l'installation sur téléphone |
| `sw.js` | permet l'utilisation hors connexion |
| `icon-192.png`, `icon-512.png` | icônes de l'application |
| `illustration.png` | image de présentation (1280 × 640), utilisable comme aperçu du dépôt GitHub |
| `.nojekyll` | indique à GitHub Pages de publier les fichiers tels quels |
| `sources/` | fichiers de travail pour modifier l'application |

## Modifier l'application

- Les exercices et leurs corrigés sont dans `sources/src/exercices.js`.
- L'interface (couleurs, textes, foot et rugby) se trouve dans `sources/src/ui.html`.
- Après une modification, reconstruire l'application depuis le dossier `sources`, sous Windows :

  ```
  powershell -ExecutionPolicy Bypass -File build.ps1
  ```

- Pour tester sur l'ordinateur, il faut [Node.js](https://nodejs.org). Lancer `node sources/serve.js` puis ouvrir `http://localhost:8642`.
- Après une mise à jour, augmenter le numéro `maths6e-v2` dans `sw.js` (et dans `build.ps1`). Sinon, les téléphones garderont l'ancienne version en mémoire.

Pour utiliser `illustration.png` comme image d'aperçu du dépôt : **Settings → General → Social preview → Edit → Upload an image**.
