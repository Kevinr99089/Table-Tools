# TableTools

🇬🇧 [English](https://github.com/Kevinr99089/Table-Tools/blob/main/README.md) | 🇫🇷 [Français](https://github.com/Kevinr99089/Table-Tools/blob/main/README_fr.md)

Application web mono-fichier (HTML/CSS/JS, aucune dépendance externe) pour tenir les scores de jeux de société et de plateau sur mobile ou tablette, posée sur la table pendant la partie. Interface en français ou anglais selon la langue du navigateur, avec un style « dessiné à la main ».

## Fonctionnalités principales

- **13 jeux de score prêts à l'emploi**, chacun avec une feuille adaptée et des règles consultables via le bouton `?` :
  - Belote (Nous / Eux)
  - Yams (bonus ≥63 automatique)
  - Tarot (contrat + donnes)
  - Rami (cartes en main = malus)
  - Uno (le plus haut gagne, fin à 500)
  - Scrabble (tour par tour)
  - Jeu du Bac (lettre aléatoire + minuteur intégré, catégories dures Q/W/X/Y/Z exclues en option)
  - 421 (3 dés + carnet)
  - Mölkky (50 points pile, retombe à 25 en cas de dépassement)
  - Skyjo (le plus bas gagne, fin à 100)
  - Pétanque (Nous / Eux, jusqu'à 13)
  - Victoires (suivi de manches gagnées : dames, échecs, puissance 4...)
  - Tableau custom (nombre de joueurs et de manches configurables)
  - Score libre (tableau générique)
- **2 outils indépendants** : dé (d6) et minuteur/sablier avec animation et préréglages (30 s à 5 min), plus réglage manuel h/min/s.
- **Mode table** : verrouillage anti-veille (Wake Lock API, avec repli vidéo silencieuse si l'API n'est pas dispo) et plein écran, avec bannière de rappel si l'un des deux est perdu (changement d'onglet, etc.).
- **Sauvegarde automatique** de toutes les feuilles en cours dans le `localStorage` du navigateur (préfixe `tt15_`) : rien n'est perdu en cas de fermeture accidentelle.
- **Bilingue automatique** (FR/EN) selon la langue du navigateur, via un dictionnaire i18n interne.
- Design « papier crayonné » (filtre SVG de distorsion, police façon écriture manuscrite) pensé pour un usage tactile, sans sélection de texte parasite.

## Utilisation

1. Ouvrir `ScoreTable.html` dans un navigateur (double-clic ou hébergement statique).
2. Choisir un jeu ou un outil depuis l'écran d'accueil.
3. Activer ☀ (anti-veille) et/ou ⛶ (plein écran) si l'appareil doit rester allumé posé sur la table.
4. Les scores se mettent à jour automatiquement ; le bouton **Retour** ou **⌂** permet de revenir à l'accueil sans perdre la partie en cours.

## Notes techniques

- Fichier unique, aucune installation ni build requis.
- Le HTML référence `manifest.json`, `icon-192.png` et `sw.js` (pour un usage en PWA installable avec icône et service worker hors-ligne) mais ces fichiers ne sont **pas inclus** dans `ScoreTable.html` : l'app fonctionne très bien sans eux (les erreurs de chargement sont silencieusement ignorées), mais il faudra les ajouter séparément si tu veux l'installer comme une vraie app sur l'écran d'accueil.
- Aucune donnée n'est envoyée à un serveur : tout reste en local sur l'appareil.
