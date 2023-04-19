---
description: Créer un point d'entrée pour le Scan FME Isogeo de type base de données pour les bases utilisant Esri SDE
---

# Scanner une base de données Esri (SDE) <i class="fa fa-database"></i>

Indiquer le chemin vers le fichier de connexion à la geodatabase d'entreprise à scanner.

## Ajouter un point d'entrée SDE {#scan_sde}

Pour créer un point d’entrée « Base de données » :

1. Dans le menu « Scan FME », créer un nouveau point d’entrée en cliquant sur « + Créer » ;
2. Sélectionnez le type « Bases de données (PostGIS, Oracle, SQL Server) » ;
3. Renseigner les champs du point d'entrée répartis en quatre sections : 
  * Informations
  * Métadonnées
  * Inclusion de données
  * Exclusion de donnée ;
4. Enregistrer et créer le point d'entrée.

#### Informations {#add_informations}

Informations générales du point d'entrée. Les champs de cette partie doivent obligatoirement être renseignés afin de pouvoir enresgistrer et créer le point d'entrée.

1. Nommer le point d’entrée ;
2. Renseigner le chemin du fichier de connexion SDE. Ce chemin doit être accessible par l'utilisateur Windows qui lance le service de Scan (voir [Configuration du compte utilisateur](/installation/server.html#compte-utilisateur)).

#### Métadonnées {#add_metadata}

La section "Métadonnées", permet de sélectionner les étiquettes à associer à toutes les fiches du point d'entrée. Les champs de cette section sont optionnels.

**NOTE** : Les métadonnées sélectionnées dans le point d'entrée seront ajoutées à toutes les fiches de ce dernier, même si elles sont ajoutées après le premier scan.

Sélectionner les métadonnées de la liste suivante à associer aux fiches de métadonnées :

* Catalogues : Tous les catalogues du groupe de travail sur app.isogeo.com ;
* Thématiques : Seules les thématiques sélectionnées ;
* Thèmes INSPIRE : Tous les thèmes INSPIRE ;
* Mot-clés : La liste de mots-clés associés **OU** la liste restreinte de mots-clés.

L'ajout de nouvelles métadonnées se fait automatiquement lors d'un Scan.

#### Inclusion de données {#add_inclusions}

La section "Inclusion de données" permet la sélection des données du point d'entrée à scanner. Seules les données correspondant au moins un des critères d'inclusion seront scannées. Les champs de cette partie sont optionnels.

Renseigner les trois champs en fonction du besoin :

* Schémas : Ajouter le(s) schéma(s) à inclure ;
* Données : Ajouter la ou les données à inclure. Le nom de la données doit obligatoirement avoir la forme suivante : schéma.nom_de_table.

Il est possible, pour les trois types d'inclusion, d'importer une liste depuis un fichier CSV (cf. [Annexe sur le format du fichier CSV](/appendices/csv.md)). Il est aussi possible de supprimer le contenu de chaque liste séparément.

#### Exclusion de données {#add_exclusions}

La section "Exclusion de données" permet la sélection des données du point d'entrée à ignorer par le Scan. Seules les données correspondant à aucun critère d'exclusion seront scannées. Les champs de cette partie sont optionnels.

Renseigner les trois champs en fonction du besoin :

* Schémas : Ajouter le(s) schéma(s) à exclure ;
* Données : Ajouter la ou les données à exclure. Le nom de la données doit obligatoirement avoir la forme suivante : schéma.nom_de_table.

Il est possible, pour les trois types d'exclusion, d'importer une liste depuis un fichier CSV (cf. [Annexe sur le format du fichier CSV](/appendices/csv.md)). Il est aussi possible de supprimer le contenu de chaque liste séparément.

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
