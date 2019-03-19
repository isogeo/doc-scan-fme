---
description: Ajouter une donnée à la carte de QGIS (canevas) avec le plugin Isogeo
---

# Ajouter une donnée à la carte {#add_data_from_metadata}

La principale finalité du plugin est de permettre à l'utilisateur final d'ajouter les données du catalogue directement à sa carte, sans se soucier de configurer les paramètres d'accès aux données sources.

## Fonctionnement

Pour pouvoir ajouter les données à l'espace de travail du logiciel SIG, le plugin se base uniquement sur les métadonnées. Pour rappel :

* **aucune donnée ne transite par notre infrastructure**
* seules les métadonnées sont utilisées et plus particulièrement les champs d'identification de la donnée source ([emplacement et nom technique](http://help.isogeo.com/admin/fr/features/documentation/md_identification.html#emplacement--nom-de-la-donn%C3%A9e))

## Options d&apos;ajout {#add_options}

Pour ajouter une donnée à la carte, la colonne "Ajouter" liste les options possibles.

Il y a plusieurs cas de figure :

* La donnée peut être ajoutée d'une seule manière. Auquel cas, la colonne "Ajouter" ne comprend qu'un bouton. Au clic, la donnée sera ajoutée à la carte.

![Donn&eacute;e ajoutable d&apos;une seule mani&egrave;re](/assets/search_results_addOk_one_fr.png)

* La donnée peut être ajoutée de plusieurs manières différentes. Auquel cas, la colonne "Ajouter" comprend une liste déroulante permettant à l'utilisateur de choisir entre les différentes options.

![Donnée ajoutable de plusieurs manières](/assets/search_results_add_OK_multi_fr.png)

* La donnée ne peut pas être ajoutée : le fichier n'est pas disponible et il n'y a pas de services renseignés \(ou ceux-ci sont mal renseignés\).

![Donnée non ajoutable - Critères non remplis](/assets/search_results_addNot_fr.png)

---

## Critères {#add_criteria}

### Données fichier {#add_files}

Le chemin vers la donnée doit être rempli dans le champ `Emplacement de la donnée` sur [https://app.isogeo.com](https://app.isogeo.com). Ce chemin doit être accessible :

* par l'utilisateur ayant lancé QGIS \(droits en lecture\);
* depuis le poste sur lequel le plugin se trouve \(en local ou via le réseau local\).

#### Cache {#filespaths_cache}

Pour améliorer les performances, le plugin intègre un système de cache minimaliste sur les chemins d'accès inaccessibles. Pour vider le cache, cliquer sur le bouton dédié dans l'onglet paramètres :

![Bouton pour vider le cache des chemins de fichiers inacessibles](/assets/settings_cache_trash_fr.png)

#### Formats supportés

##### Vecteur

* DXF
* DGN
* Esri FileGDB
* Esri shapefile
* MapInfo tab

##### Raster

* ECW
* Esri ascii grid
* Geotiff
* Intergraph gdb
* JPEG
* PNG
* XYZ

### Données PostGIS {#add_postgis}

Une table PostGIS pourra être ajoutée par le plugin dans les conditions suivantes :

* La connexion à la base de données dans laquelle elle se trouve a été enregistrée dans QGIS
* L’option “Enregistrer le nom d’utilisateur et le mot de passe” a été choisie
* La fiche documentant la table PostGIS a été créée à partir du scan FME Isogeo. En créant une fiche manuellement dans [https://app.isogeo.com](https://app.isogeo.com), il est impossible de renseigner le champ _name_ nécessaire à l’ajout de la table.

### Services géographiques {#add_services}

Le plugin supporte les couches de services documentés automatiquement et associés aux métadonnées de données.

Consulter [l'aide en ligne au sujet du recensement automatisé des services et de l'association couche de service / donnée cataloguée](http://help.isogeo.com/admin/fr/features/inventory/md_services/srv_intro.html).

Il supporte également les URLs de couches de services renseignées manuellement dans la métadonnée. Si cette méthode \(dépréciée\) est utilisée :

* L’url doit contenir la base de l’url du service géographique
* Elle doit également contenir le nom de la couche du service à afficher.

Consulter [l'aide en ligne sur les syntaxes de documentation manuelle des couches de services](http://help.isogeo.com/admin/fr/features/publish/webservices.html).

#### Formats de services supportés

* Esri Feature Service \(EFS\)
* Esri Map Service \(EMS\)
* Web Feature Service \(WFS\)
* Web Map Service \(WMS\)
* Web Map Tile Service \(WMTS\)

> **Note importante**  
> Si le titre de la couche comprend des caractères spéciaux ou des accents, il est possible que la couche ne puisse pas être affichée convenablement dans QGIS. Il s’agit d’un problème de gestion de l'encodage par l’API PyQGIS.
