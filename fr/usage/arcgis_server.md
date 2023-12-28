---
description: Créer un point d'entrée de type ArcGIS Server pour le Scan FME Isogeo
---

# ArcGIS Server

Cette fonctionnalité permet d'automatiser : 

* la documentation de vos services (EMS, EFS et WFS) publiés avec ArcGIS Server en créant ou mettant à jour leurs fiches de métadonnées de services 
* la création des associations entre couches / tables de service et fiches de métadonnées de données (cf. [Associer une fiche de donnée avec une couche de service](https://help.isogeo.com/admin/fr/features/inventory/md_services/srv_association.html)).

> NB : Pour des raisons de disponibilités et de performances de l'API Isogeo, cette fonctionnalité n'est utilisable que par l'équipe Isogeo. Si vous souhaitez recenser automatiquement vos services, veuillez vous rapprocher de votre interlocuteur Isogeo pour mettre en oeuvre la [prestation dédiée](https://www.isogeo.com/actualites/nouvelle-prestation-recensement-des-services-arcgis-server-et-associations-aux-fiches-de-donnees/318).

## Caractéristiques et précisions {#precisions}

* les services doivent être publiés avec ArcGIS Pro
* l'[utilisateur du Scan](/installation/server#user) doit avoir accès en lecture au répertoire `arcgisinput` d'ArcGIS Server, situé par défaut dans le répertoire `C:\arcgisserver\directories\arcgissystem\`
* tous les dossiers d'ArcGIS Server sont explorés et il est donc recommandé d'indiquer une granularité assez fine (quelques dizaines de services maximum par point d'entrée) ;
* il est possible d'exclure des formats, des dossiers et des services particuliers ;

### Métadonnées récupérées

Pour chaque service seront récupérées les informations suivantes :
* l’url du service, 
* le titre, le résumé et les balises indiqués à la publication du service 
 * Si la chaîne de caractères d'une balise ArcGIS Server est identique à une thématique / thème INSPIRE, alors celui-ci est affecté à la fiche de service 
![Métadonnées renseignées lors de la publication du service avec ArcGIS Pro](/assets/metadata_publication_service_ags.png)
* l’emprise du service sous forme de bbox
* le format et la version de format
* Les identifiants, les titres et le type (layer, group, table) des ressources fournies par le service
 * Si les données sources des couches ont été scannées par le Scan, l’association entre les couches et la fiche de métadonnées est automatiquement établie selon le critère du nom (schema.table).

#### Mise à jour

Lors d'une mise à jour des métadonnées du service, les champs suivants sont écrasés :
* les informations sur les couches / tables du service avec leurs identifiants et leurs titres
* l’emprise du service sous forme de bbox
* la version de format

En revanche, le titre et le résumé ne sont jamais écrasés car l'utilisateur peut les avoir modifiés manuellement.
Les mots-clés, thématiques et thèmes Inspire supplémentaires sont ajoutés tandis que ceux supprimés ne sont pas retirés de la fiche existante. 

### Ajouter un répertoire de fichiers à scanner {#add_repertory}

Pour créer un point d’entrée « ArcGIS Server » :

1. Dans le menu « Scan FME », créer un nouveau point d’entrée en cliquant sur « + Créer » ;
2. Sélectionnez le type « ArcGIS Server » ;
3. Renseigner les champs du point d'entrée répartis en quatre sections : 
  * Informations 
  * Métadonnées 
  * Inclusion de services 
  * Exclusion de services ;
4. Enregistrer et créer le point d'entrée.

#### Informations {#add_informations}

Informations générales du point d'entrée : Les champs de cette partie doivent obligatoirement être renseignés afin de pouvoir enregistrer et créer le point d'entrée.

1. Nommer le point d’entrée. Exemple : `Services AGS`;
2. Renseigner le chemin d’accès au répertoire `arcgisinput` ou un sous-dossier de celui-ci contenant les services à scanner. Exemple : `//serveur/partage/arcgisinput/demo`
3. Renseigner l'url de base de l'ArcGIS Server. Exemple : `https://carto.isogeo.net`

    ![Renseigner les informations du point d'entrée ArcGIS Server](/assets/New entrypoint - arcgis server.png)

#### Métadonnées {#add_metadata}

La section "Métadonnées", permet de sélectionner les étiquettes à associer à toutes les fiches du point d'entrée. Les champs de cette section sont optionnels.

**NOTE** : Les métadonnées sélectionnées dans le point d'entrée seront ajoutées à toutes les fiches de ce dernier, même si elles sont ajoutées après le premier scan.

Sélectionner les métadonnées de la liste suivante à associer aux fiches de métadonnées :

* Catalogues : Tous les catalogues du groupe de travail sur app.isogeo.com ;
* Thématiques : Seules les thématiques sélectionnées ;
* Thèmes INSPIRE : Tous les thèmes INSPIRE ;
* Mot-clés : La liste de mots-clés associés **OU** la liste restreinte de mots-clés.

L'ajout de nouvelles métadonnées se fait automatiquement lors d'un Scan.

#### Inclusion de services {#add_inclusions}

La section "Inclusion de services" permet la sélection des services du point d'entrée à scanner. Seules les services correspondant à au moins un des critères d'inclusion seront scannées. Les champs de cette partie sont optionnels.

Renseigner les trois champs en fonction du besoin :

* Formats des services : Sélectionner un ou plusieurs formats, de la liste prédéfinie, à inclure ;
* Dossiers : Ajouter le(s) sous-dossier(s) à inclure ;
* services : Ajouter le(s) nom(s) du ou des services à inclure.

Il est possible, pour les trois types d'inclusion, d'importer une liste depuis un fichier CSV (cf. [Annexe sur le format du fichier CSV](/appendices/csv.md)). Il est aussi possible de supprimer le contenu de chaque liste séparément.

#### Exclusion de services {#add_exclusions}

La section "Exclusion de services" permet la sélection des services du point d'entrée à ignorer par le Scan. Seules les services correspondant à aucun critère d'exclusion seront scannées. Les champs de cette partie sont optionnels.

Renseigner les trois champs en fonction du besoin :

* Formats de services : Sélectionner un ou plusieurs formats, de la liste prédéfinie, à exclure ;
* Dossiers : Ajouter le(s) sous-dossier(s) à exclure ;
* services : Ajouter le(s) nom(s) du ou des services à exclure.

Il est possible, pour les trois types d'exclusion, d'importer une liste depuis un fichier CSV (cf. [Annexe sur le format du fichier CSV](/appendices/csv.md)). Il est aussi possible de supprimer le contenu de chaque liste séparément.

#### Associations automatiques {#associations}

Cette fonctionnalité permet de forcer la création des associations entre les couches des services scannées et les fiches de données présentes dans l'inventaire même si le service est inchangé. En clair, cela permet de créer l'association entre une donnée qui aurait été scannée en base de donnée après le scan du service qui publie cette même donnée. 
Cette case doit donc être cochée uniquement dans ce cas précis.
