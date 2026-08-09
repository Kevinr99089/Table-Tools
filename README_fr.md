# Table Tools

🇬🇧 [English](https://github.com/Kevinr99089/Table-Tools/blob/main/README.md) | 🇫🇷 [Français](https://github.com/Kevinr99089/Table-Tools/blob/main/README_fr.md)

**Application en ligne :** https://kevinr99089.github.io/Table-Tools/

Application web mono-fichier (HTML/CSS/JS, aucune dépendance externe) pour tenir les scores de jeux de société et de plateau sur mobile ou tablette, posée sur la table pendant la partie. Interface en français ou en anglais selon la langue du navigateur, avec un style « dessiné à la main ». Publiée via GitHub Pages et installable en tant que PWA.

## Fonctionnalités principales

- **8 jeux de score**, chacun avec une feuille adaptée et des règles consultables via le bouton `?` :
  - Belote (Nous / Eux)
  - Yams (bonus ≥63 automatique)
  - Tarot (contrat + donnes)
  - Rami (cartes en main = malus)
  - Uno (le plus haut gagne, fin à 500)
  - Scrabble (tour par tour)
  - Skyjo (le plus bas gagne, fin à 100)
  - Mölkky (50 points pile, retombe à 25 en cas de dépassement)
- **1 jeu de catégories** : le jeu du Bac (lettre aléatoire + minuteur intégré, lettres difficiles Q/U/W/X/Y/Z exclues en option)
- **3 feuilles libres** : un compteur de victoires (dames, échecs, puissance 4...), un tableau custom (nombre de joueurs et de manches configurables) et un score libre (tableau générique)
- **2 outils indépendants** : un dé (d6) et un minuteur/sablier avec animation de retournement ; le temps se règle manuellement — en appuyant directement sur la valeur H/MIN/SEC pour la saisir, ou via les boutons +/− de chaque unité
- **Chaque feuille de score** permet d'ajouter/retirer des joueurs, dispose d'un champ date optionnel, d'un bouton annuler (retire la dernière manche) et d'un bouton reset — les actions destructrices demandent une confirmation par un second appui
- **Alerte de fin de minuteur configurable** : choix d'un son intégré (cloche, sifflet, tambour, douce) ou d'un fichier audio personnalisé (max ~1,5 Mo), volume réglable, écran clignotant et vibration (si disponible)
- **Mode table** : verrouillage anti-veille (Wake Lock API, avec repli vidéo silencieuse si l'API n'est pas disponible) et plein écran, avec bannière de rappel si l'un des deux est perdu (changement d'onglet, etc.)
- **Sauvegarde automatique** de toutes les feuilles en cours dans le `localStorage` du navigateur (préfixe `tt15_`) : rien n'est perdu en cas de fermeture accidentelle
- **Bilingue automatique** (FR/EN) selon la langue du navigateur, via un dictionnaire i18n interne
- **Installable en tant que PWA**, avec une icône sur l'écran d'accueil et un fonctionnement hors ligne via un service worker
- Design « papier crayonné » (filtre SVG de distorsion, police façon écriture manuscrite) pensé pour un usage tactile, sans sélection de texte parasite

## Utilisation

1. Ouvrir l'application sur [kevinr99089.github.io/Table-Tools](https://kevinr99089.github.io/Table-Tools/) — aucune installation requise.
2. Il est possible de l'installer comme une application depuis le menu du navigateur (« Installer l'application » / « Ajouter à l'écran d'accueil ») pour obtenir une icône sur l'écran d'accueil et un accès hors ligne.
3. Choisir un jeu ou un outil depuis l'écran d'accueil.
4. Activer ☀ (anti-veille) et/ou ⛶ (plein écran) si l'appareil doit rester allumé posé sur la table.
5. Les scores se mettent à jour automatiquement ; le bouton **Retour** ou **⌂** permet de revenir à l'accueil sans perdre la partie en cours.

## Notes techniques

- Front-end mono-fichier, aucune étape de build requise.
- Hébergée et servie via GitHub Pages ; les fichiers PWA (`manifest.json`, `icon-192.png`, `sw.js`) sont inclus et permettent l'installation avec icône sur l'écran d'accueil ainsi que la mise en cache hors ligne via le service worker.
- Aucune donnée n'est envoyée à un serveur : tout reste en local sur l'appareil.
