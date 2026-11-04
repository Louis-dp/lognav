# Log de navigation IFR — application hors ligne (iPad)

Reprise complète du fichier Excel « Log de navigation IFR » :
- **Log 1 / Log 2 / Log 3** : feuilles Étape 1, 2 et 3 (log, dégagement, carburant, journal), log vierge. Chaque étape part de l'arrivée de la précédente et reprend le pétrole restant (+ complément d'avitaillement).
- **Cougar** : Perfos étape 1 / 2 / 3, Centrage.
- **Fennec** : Perfo étape 1 / 2 / 3 (abaques).
- **Cartons** : Carton Perfo IFR 1 / 2 / 3.
- **Données** : trajets (enregistrés depuis chaque log, rechargeables dans le Log 1, 2 ou 3), base de points, machines et masses, réglages. Bouton « Nouveau vol » dans chaque log pour tout vider.

Les perfos, centrages et cartons sont calculés par un moteur qui exécute les formules d'origine du classeur
(fichier `classeur.json`, généré depuis l'Excel). Les feuilles lisent automatiquement le log.

## Mise en ligne (GitHub Pages)
1. Sur GitHub, créer un dépôt (ex. `log-ifr`) ou un dossier dans le dépôt des autres applis.
2. Déposer **tous les fichiers** de ce dossier, tous au même niveau (pas de sous-dossier) : `index.html`, `sw.js`, `manifest.json`, les 3 icônes et les fichiers `.json` (points, classeur, feuilles, trajets, types, wmm, points_info).
3. Settings → Pages → Branch `main` / root → Save.
4. Sur l'iPad : ouvrir l'adresse dans Safari → Partager → « Sur l'écran d'accueil ». Ouvrir une première fois avec du réseau ; ensuite tout fonctionne sans réseau.

## Mettre à jour les données pour toutes les tablettes
- Base de points : `points.json`.
- Trajets communs : `trajets.json` (mêmes colonnes que l'onglet « Trajets » de l'Excel).
- Types d'appareils : `types.json`.
- Abaques / formules (nouvelle version de l'Excel) : `classeur.json` et `feuilles.json` sont à régénérer depuis le nouveau fichier.
Après une modification, changer `CACHE = 'logifr-v…'` dans `sw.js` pour forcer la mise à jour sur les tablettes.

## Données saisies
Log en cours, perfos, trajets perso, points ajoutés et machines restent dans la tablette ;
utiliser Exporter / Importer (onglet Données) pour les partager.
