---
description: FAQ et comment résoudre les problèmes avec le plugin Isogeo pour QGIS
---

# Support et questions fréquentes

## Comment signaler un comportement anormal ? {#report}

Si vous obtenez un message d'erreur ou bien vous constatez un comportement anormal, voici la procédure à suivre :

* vérifier dans cette documentation si par hasard rien ne correspond à une explication du comportement constaté ;\)
* regarder l'onglet dédié à Isogeo dans la fenêtre des messages de QGIS :

!["Ouvrir la fenêtre des messages de QGIS"](/assets/qgis_log_view_tab_isogeo_fr.png)

Le problème persiste et signe ? Le \(dys\)fonctionnement est incompréhensible ?

Il faut alors cliquer sur le bouton dédié au signalement (porte-voix rouge) ou directement [créer un ticket](https://github.com/isogeo/isogeo-scan-fme/issues) en :

* joignant une capture de l'onglet de la fenêtre messages
* et _surtout le fichier log\_isogeo\_plugin.log_ situé dans le dossier `_logs` du dossier d'installation du plugin \(`C:\Users\%USERNAME%\.qgis2\python\plugins` pour Windows ou `/home/$USER/.qgis2/python/plugins` pour Debian\).

Pour y accéder, il suffit de cliquer sur le bouton dédié dans l'onglet `Paramètres` :

!["Paramètres - Boutons log et signalement"](/assets/settings_resources_fr.png)

---

## Questions fréquentes {#faq}

### Pourquoi n'y a t'il aucune donnée dans mon plugin ? {#nodata}

Vérifier qu'au moins un partage alimente l'application : voir [comment partager à l'application depuis Isogeo](/usage/configuration.md).

### Pourquoi aucun résultat n'est ajoutable ? {#not_add_option}

Pour qu'une donnée soit ajoutable à la carte \(canevas cartographique selon le vocabulaire QGIS\), il faut que des informations le permettant soient cataloguées dans la métadonnée. Essayer également de vider le cache.

Pour en savoir plus, [consulter la section dédiée dans la documentation](/usage/display.md).

### Pourquoi mon service WMS ne s'affiche pas alors que sa légende est bien présente ? {#wms_encoding}

Il peut y avoir plusieurs raisons :

* le service WMS n'est pas conforme aux exigences de QGIS ;
* des caractères spéciaux sont présents dans certains des intitulés \(titre, étiquettes légende...\) et l'encodage n'est pas conforme ;
* le style par défaut de la couche du WMS contient une anomalie ;

### L'ajout de donnée prend-il en compte les fichiers de symbologie \(.qlr\) ? {#qlr_handling}

Oui, si le qlr se nomme de la même façon que le fichier de la donnée source et est situé dans le même dossier.

### Pourquoi le thème de QGIS est-il modifié ? {#qgis_theme}

Il existe plusieurs thèmes pour QGIS \(Préférence/Options/Général/Style\). Certains ne permettent pas d'afficher les cases à cocher dans la liste des mots-clefs. Il s'agit des thèmes _Macintosh \(aqua\)_ et _Cleanlooks_. A l'ouverture du plugin, celui-ci détecte le thème et le modifie automatiquement. Après redémarrage de QGIS, le thème _Plastique_ est configuré et le plugin peut fonctionner dans les meilleurs conditions.

N.B: Ce problème affecte principalement les utilisateurs de QGIS sous MacOS car le thème par défaut n'est pas adapté.
