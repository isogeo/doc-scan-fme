# ArcSDE <i class="fa fa-database"></i>

## Scanner un point d'entrée SDE {#scan_sde}

1. Dans le menu « Scan FME », créer un nouveau point d’entrée en cliquant sur « + Nouveau » ;
2. Sélectionner le type « Base de données » ;
3. Nommer le point d’entrée. Exemple : Base de références ;
4. Sélectionner le type de base de données sur lequel est installée la cartouche spatial SDE ;
5. Dans `Paramètres de la geodatabase ESRI`, cocher `Oui`
6. Indiquer le chemin vers le fichier de connexion (.sde), ce chemin doit être accessible par l'utilisateur `isogeo`
7. Sauvegarder.

    ![Nouveau point d&apos;entrée base](/assets/scanFME_new_DB_ready.png "Le nouveau point d&apos;entrée est prêt à être scanné")

## Bonnes pratiques

Il est conseillé de créer un dossier sur le serveur où est installé le service Isogeo pour stocker les fichiers SDE.
Ensuite, il suffit de copier-coller les fichiers SDE générés sur ArcCatalog par l'administrateur SIG dans ce dossier.
Pour info, les fichiers SDE sont généralement stockés par ArcCatalog au chemin suivant : `C:\Users\Nom_utilisateur\AppData\Roaming\ESRI\Desktop10.6\ArcCatalog\`.

## Générer un fichier de connexion SDE depuis ArcCatalog {#generate_sde}

1. Ouvrir ArcCatalog ;
2. Ajouter une connexion aux bases de données (cf. figure ci-dessous) ;
3. Renseigner les paramètres de connexion à la base de donnée ;
4. La liste déroulante des bases de données accessibles se génère ;
5. Selectionner la base concernée, valider et vérifier que la liste des tables s'affiche dans l'arborescence.
6. Ensuite, ouvrir les propriétes de la connexion pour récupérer le chemin vers le fichier SDE (onglet Général, Nom)

Pour plus d'informations, veuillez consulter la [documentation officielle](http://desktop.arcgis.com/fr/arcmap/latest/manage-data/using-arccatalog/connecting-to-an-enterprise-geodatabase-from-the-catalog-window.htm).

!["Ajouter une connexion aux bases de données"](/assets/scanFME_sde_arcCatalog.png)
