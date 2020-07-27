---
description: Créer un point d'entrée pour le Scan FME Isogeo de type base de données pour les bases utilisant Esri SDE
---

# Scanner une base de données Esri (SDE) <i class="fa fa-database"></i>

Indiquer le chemin vers le fichier de connexion à la geodatabase d'entreprise à scanner.

## Ajouter un point d'entrée SDE {#scan_sde}

1. Dans le menu « Scan FME », créer un nouveau point d’entrée en cliquant sur « + Nouveau...» ;
2. Sélectionner le type « Géodatabase d’entreprise Esri (SDE) » ;
3. Nommer le point d’entrée.
4. Dans `Fichier de connexion`, indiquer le chemin vers le fichier de connexion (.sde), ce chemin doit être accessible par l'utilisateur Windows qui lance le service de Scan (voir [Configuration du compte utilisateur](/installation/server.html#compte-utilisateur))
5. Choississez dans quel(s) catalogue(s) vous souhaitez ajouter automatiquement les nouvelles données scannées en le(s) sélectionnant (en général 1 catalogue de suivi et 1 catalogue thématique) 
6. Sauvegarder.

![Nouveau point d'entrée SDE](/assets/new_DB_sde_ready.png)

## Bonnes pratiques

Il est conseillé de créer un dossier sur le serveur où est installé le service Isogeo pour stocker les fichiers SDE.
Ensuite, il suffit de copier-coller les fichiers SDE générés sur ArcCatalog par l'administrateur SIG dans ce dossier.
Pour info, les fichiers SDE sont généralement stockés par ArcCatalog au chemin suivant : `C:\Users\Nom_utilisateur\AppData\Roaming\ESRI\Desktop10.6\ArcCatalog\`.

### Générer un fichier de connexion SDE depuis ArcCatalog {#generate_sde}

1. Ouvrir ArcCatalog ;
2. Ajouter une connexion aux bases de données (cf. figure ci-dessous) ;
3. Renseigner les paramètres de connexion à la base de donnée ;

    !["Ajouter une connexion aux bases de données"](/assets/sde_arcCatalog.png)

4. La liste déroulante des bases de données accessibles se génère ;
5. Sélectionner la base concernée, valider et vérifier que la liste des tables s'affiche dans l'arborescence.
6. Ensuite, ouvrir les propriétes de la connexion pour récupérer le chemin vers le fichier SDE (onglet Général, Nom)

Pour plus d'informations, veuillez consulter la [documentation officielle](http://desktop.arcgis.com/fr/arcmap/latest/manage-data/using-arccatalog/connecting-to-an-enterprise-geodatabase-from-the-catalog-window.htm).
