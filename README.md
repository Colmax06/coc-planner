# CoC Planner

Planificateur d’améliorations pour **Clash of Clans** : village principal et base des ouvriers.
Application web statique (HTML + JavaScript, aucun serveur), pensée pour le téléphone et hébergeable gratuitement sur GitHub Pages.

> Contenu non officiel, non approuvé par Supercell. Voir la [politique de contenu de fans](https://supercell.com/en/fan-content-policy/). Clash of Clans est une marque de Supercell, dont les images appartiennent à Supercell.

## Ce que fait le site

- **Import du compte** en un geste : Paramètres → Plus de paramètres → *Data Export* → Copier, puis « 📥 Mettre à jour » colle automatiquement le presse-papier.
- **Progression** par catégorie (structures, laboratoire, héros, familiers, équipement, murailles) pour chaque village.
- **Ouvriers et laboratoire** : améliorations en cours lues dans l’export, plus lancement d’une amélioration depuis la file avec la durée issue des données du jeu.
- **Calendrier** façon diagramme de Gantt, avec zoom jusqu’à la minute et heure de fin exacte.
- **File d’attente** planifiée automatiquement sur l’ouvrier qui se libère le plus tôt.
- **Reste à faire** pour votre HDV, avec onglets Constructions / Laboratoire, tris et filtres (nom, niveau, ressource).
- **Bâtiments et coût pour finir** : un exemplaire par ligne, coûts, durées, « Niveau max » en vert.
- **Réglages** : Gold Pass, nombre d’ouvriers (1 à 6 au village, 1 à 4 à la base des ouvriers), artisans, tour de l’horloge, horaires sans connexion.
- **Mode push** : prérequis du HDV, lancement du HDV dès qu’ils sont terminés, puis améliorations importantes pendant qu’il s’améliore.
- **Notifications** et **export .ics** (un événement par amélioration, avec alarme).

## Utiliser

1. Ouvrir le site (par exemple `https://colmax06.github.io/coc-planner/`).
2. Toucher « 📥 Mettre à jour » dans la carte du haut et suivre le tutoriel.
3. Régler le Gold Pass et le nombre d’ouvriers.

Toutes les données restent dans le navigateur (`localStorage`). Rien n’est envoyé nulle part.

## Héberger sur GitHub Pages

Déposer ces fichiers à la racine du dépôt, puis activer *Settings → Pages → Deploy from a branch*.

```
index.html   page complète (CSS et JavaScript inclus)
data.js      données du jeu : niveaux, durées, coûts, paliers de HDV
sw.js        service worker (notifications système sur Android)
icons/       icônes WebP : {identifiant}-{niveau}.webp, th-N.webp, bh-N.webp
README.md
LICENSE.txt
```

Sans `sw.js`, tout fonctionne sauf les notifications système sur téléphone. Sans `icons/`, des emojis s’affichent à la place des images.
GitHub limite l’envoi par navigateur à environ 100 fichiers à la fois : pour `icons/` (≈1250 fichiers), utiliser git ou GitHub Desktop.

## Données et crédits

- Données et images : [chiefpansancolt/clash-of-clans-data](https://github.com/chiefpansancolt/clash-of-clans-data) (licence MIT pour le dépôt ; les images du jeu restent la propriété de Supercell).
- Règles des artisans : aide officielle de Supercell, [Helpers & The Helper Hut](https://support.supercell.com/clash-of-clans/en/articles/helpers-2.html).
- Prérequis de HDV et conseils de montée : Clash of Clans Wiki et plusieurs guides, détaillés dans `info.md`.

## Limites

- Les données du jeu datent de leur dernière mise à jour : un nouveau HDV ou un équilibrage peut manquer.
- Certaines règles sont des hypothèses signalées dans le site et dans `info.md` (par exemple la recharge de la tour de l’horloge).
- Le site ne reproduit pas l’algorithme de recommandation de Supercell, qui n’est pas public.

## Licence

[MIT](LICENSE.txt) © 2026 Colmax06
