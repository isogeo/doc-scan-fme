# ArcSDE <i class="fa fa-database"></i>

## Générer un fichier de connexion SDE depuis ArcCatalog

1. Se connecter au serveur où le service Isogeo et FME sont installés ;
2. Ouvrir ArcCatalog ;
3. Ajouter une connexion aux bases de données (cf. figure ci-dessous) ;
4. Renseigner les paramètres de connexion à la base de donnée ;
5. La liste déroulante des bases de données accessibles se génère ;
6. Selectionner la base concernée, valider et vérifier que la liste des tables s'affiche dans l'arborescence.
7. Ensuite, ouvrir les propriétes de la connexion pour récupérer le chemin vers le fichier SDE (Onglet Général, Nom)

Pour plus d'informations, veuillez consulter la [documentation officielle](http://desktop.arcgis.com/fr/arcmap/latest/manage-data/using-arccatalog/connecting-to-an-enterprise-geodatabase-from-the-catalog-window.htm)

!["Ajouter une connexion aux bases de données"](/assets/sde_arcCatalog.png)

## Scanner un point d'entrée SDE

1. Dans le menu « Scan FME », créer un nouveau point d’entrée en cliquant sur « + Nouveau » ;
2. Sélectionner le type « Base de données » ;
3. Nommer le point d’entrée. Exemple : Base de références ;
4. Sélectionner le type de base de données sur lequel est installée la cartouche spatial SDE ;
5. Dans `Paramètres de la geodatabase ESRI`, cocher `Oui`
6. Indiquer le chemin vers le fichier de connexion (.sde), généralement les fichiers SDE sont stockés au chemin suivant `C:\Users\Nom_utilisateur\AppData\Roaming\ESRI\Desktop10.6\ArcCatalog\`
7. Sauvegarder.

    ![Nouveau point dentrée base](/assets/new_DB_ready.png "Le nouveau point dentrée est prêt à être scanné")