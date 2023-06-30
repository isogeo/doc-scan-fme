---
description: Paramètres logiciels (FME, ArcGIS) du service client du Scan FME (Isogeo)
---
# Logiciels

## Installation de FME Desktop {#fme_installation}

FME Desktop doit être installé et parfaitement configuré pour accéder et manipuler vos données géographiques. Points de vérification :

* édition de la licence (cf. [Formats pris en charge par le scan](/usage/formats.md)) :
  * Professional Edition ;
  * Esri Edition ;
  * Database Edition ;
* jeton de licence FME disponible au moment du scan ;
* architecture 32 ou 64 bits selon configuration Esri ou Oracle ;
* plugins spécifiques.

À ce jour, les versions de FME supportées sont :

* de FME Desktop 2020.x;
* à FME Desktop 2022.x

Pour télécharger FME, consulter le [site de safe](https://www.safe.com/support/downloads/#past-versions).

Pour plus d’informations, consulter la [matrice des formats et versions de FME](https://www.safe.com/fme/formats-matrix/) ;

## Cas spécifique pour les formats Esri {#esri}

Selon votre installation Esri, voici la version de FME à installer. Consulter également [l'article dédié [en]](https://knowledge.safe.com/articles/1517/notes-on-fme-and-esri-versions-and-compatibility.html) aux compatibilités entre FME et ArcGIS Desktop/Pro sur le site de Safe, éditeur de FME.

|                                Installation Esri                                |     Version de FME    |
|:-------------------------------------------------------------------------------:|:---------------------:|
|                             ArcGIS Desktop (32 bits)                            | FME Desktop (32 bits) |
| ArcGIS Desktop (32 bits) avec ArcGIS Desktop Background Geoprocessing (64-bits) | FME Desktop (64 bits) |
|                               ArcGIS Pro (64 bits)                              | FME Desktop (64 bits) |

### Avec ArcMap et FME en version 64 bits {#esri_arcmap}

Pour que la licence ArcMap fonctionne avec FME en version 64 bits, il faut :
* installer le [ArcGIS Desktop Background Geoprocessing 64 bits](https://desktop.arcgis.com/fr/arcmap/latest/analyze/executing-tools/64bit-background.htm).
* ajouter une variable d'environnement système `SDEHOME` dont la valeur est `C:\Program Files (x86)\ArcGIS\Desktop10.8\bin64` (cet emplacement peut différer dépendamment de votre installation et de votre version du logiciel ArcMap)

### Avec ArcGIS Pro {#esri_argispro}

Pour que la licence ArcGIS Pro fonctionne, il faut :
* authentifier le logiciel avec l'utilisateur qui lance le service, c'est à dire qu'il faut se connecter à distance au serveur avec la session de l'utilisateur Isogeo puis ouvrir ArcGIS Pro et l'authentifier.
* paramétrer FME pour utiliser l'interpréteur Python installé avec ArcGIS Pro : depuis FME Desktop, menu `Tools` > `FME Options` > onglet `Translations` > rubrique `Python Interpreter` :
  * `Preferred Python Interpreter` : sélectionner `Use Custom Interpreter...` dans la liste déroulante puis indiquer `C:\Program Files\ArcGIS Pro\bin\Python\envs\arcgispro-py3\python3.dll` (cet emplacement peut différer dépendamment de votre installation du logiciel ArcGIS Pro)
  * `Python Home (PYTHONHOME)` : indiquer `C:\Program Files\ArcGIS Pro\bin\Python\envs\arcgispro-py3`" (cet emplacement peut différer dépendamment de votre installation du logiciel ArcGIS Pro)

## Base de données Oracle {#oracle}

Pour accéder à une base Oracle, que la cartouche spatiale soit Oracle Spatial ou ArcSDE, il est nécessaire d'avoir installé une instance de client : [Oracle Instant Client Basic Light](https://www.oracle.com/database/technologies/instant-client.html).

* [téléchargeable ici en 64 bits](https://www.oracle.com/database/technologies/instant-client/winx64-64-downloads.html), si FME a été installé en version 64 bits
* [téléchargeable ici en 32 bits](https://www.oracle.com/database/technologies/instant-client/microsoft-windows-32-downloads.html), si FME a été installé en version 32 bits

De plus, pour que les tables et les vues Oracle soient lues par FME, il faut s'assurer que les valeurs indiquées dans [cet article](https://community.safe.com/s/article/adding-metadata-entries-for-oracle-spatial-tables) sont bien présentes dans la table `user_sdo_geom_metadata`, sinon il faut les ajouter comme précisé.

## Cas spécifique des données Canadienne {#CSRS}

Pour scanner les données géographiques dont les entitées sont localisées sur le territoire du Canada, il peut être nécessaire de charger un fichier de transformation de grille particulier dans le logiciel FME Workbench. Cela concerne les données dont l'interprétation géométrique implique le datum CSRS.

Le fichier de transformation de grille NAD83_to_CSRS est téléchargeable depuis le [site Internet du Gouvernement du Canada](https://webapp.csrs-scrs.nrcan-rncan.gc.ca/geod/data-donnees/transformations.php?locale=fr). Une fois téléchargé, il faut le charger dans FME Workbench : Tools > FME Options > Coordinate systems > chercher NAD83_to_CSRS dans la liste > cliquer sur "Éditer" > indiquer l'emplacement du fichier.

Pour plus d'informations :

* [*Where to source Canadian grid shift files not included with FME*](https://community.safe.com/s/article/where-to-source-canadian-grid-shift-files-not-incl)
* [*Canadian Spatial Reference System (CSRS) High Precision Datum*](https://community.safe.com/s/article/canadian-spatial-reference-system-csrs-high-precis)
* [*Where can I find the CSRS transformation grids for the Province of Quebec?*](https://community.safe.com/s/question/0D54Q000080hTpjSAE/where-can-i-find-the-csrs-transformation-grids-for-the-province-of-quebec)