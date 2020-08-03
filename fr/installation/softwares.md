---
description: Paramètres logiciels (FME, ArcGIS) du service client du Scan FME (Isogeo)
---
# Logiciels

## Installation de FME Desktop {#fme_installation}

FME Desktop doit être installé et parfaitement configuré pour accéder et manipuler vos données géographiques. Points de vérification :

* édition de la licence (Professionnal ou Esri Edition pour SDE)  ;
* jeton de licence FME disponible au moment du scan ;
* architecture 32 ou 64 bits ;
* plugins spécifiques.

À ce jour, les versions de FME supportées sont :

* de FME Desktop 2013 SP4 ;
* à FME Desktop 2018.

Ainsi que les Service Pack associés.

Pour télécharger FME :

* la dernière version compatible [en 32 bits](https://downloads.safe.com/fme/2018/fme-desktop-2018.1.2.1-b18592-win-x86.msi) ou [en 64 bits](https://downloads.safe.com/fme/2018/fme-desktop-2018.1.2.1-b18592-win-x64.msi) ;
* une [ancienne version spécifique](https://www.safe.com/support/support-resources/fme-downloads/archived/).

Pour plus d’informations, veuillez contacter votre distributeur FME.

### Cas spécifique pour les formats Esri {#esri}

Selon votre installation Esri, voici la version de FME à installer.

|                                Installation Esri                                |     Version de FME    |
|:-------------------------------------------------------------------------------:|:---------------------:|
|                             ArcGIS Desktop (32 bits)                            | FME Desktop (32 bits) |
| ArcGIS Desktop (32 bits) avec ArcGIS Desktop Background Geoprocessing (64-bits) | FME Desktop (64 bits) |
|                               ArcGIS Pro (64 bits)                              | FME Desktop (64 bits) |

Cependant, pour éviter tout problème de compatibilité, il est recommandé de mettre en place la première configuration ArcGIS Desktop et FME 32 bits.

<!-- 1. Tout d'abord, il faut **la version 32 bits de FME** et si possible l'édition Esri
2. Ensuite :
    * soit ArcGIS Desktop 32 bits sur la même machine avec une licence disponible pendant toute la durée du Scan - méthode recommandée ;
    * soit installer les librairies SDE sur la machine où est installée votre FME ([voir cet article](https://knowledge.safe.com/articles/358/arcsde-libraries-required-for-the-esri-arcsde-sde3.html)) - méthode plus complexe.
3. Si ArcGIS est en licence flottante liée à un serveur de licences distant, ajouter la variable d'environnement `ARCGIS_LICENCE_FILE` (voir [la doc Esri](http://resources.arcgis.com/fr/help/install-guides/license-manager/10.1/index.html#/Defining_port_host_to_one_or_more_license_servers/00790000000t000000/)) avec pour valeur le port et l'adresse de votre serveur de licence (information située dans ArcGIS Administrator) :

    ![Scan - ArcGIS SDE license](/assets/install_SDE_env_var_arcgis_licensing.png "Variable d'environnement pour le serveur de licence d'ArcGIS") -->

Pour aller plus loin :

* consulter cet [article](https://www.inser.ch/fr/content/fme-et-arcgis-desktoparcgis-pro) sur la compatibilité FME/Esri ;
* consulter la [matrice des formats et versions de FME](https://www.safe.com/fme/formats-matrix/#search=arcsde) ;
* consulter [l'article dédié [en]](https://knowledge.safe.com/articles/1517/notes-on-fme-and-esri-versions-and-compatibility.html) à ces questions d'interopérabilité sur le site de Safe, éditeur de FME.

### Oracle {#oracle}

Pour pouvoir se connecter aux bases Oracle, il est nécessaire d'avoir installé le client Oracle Instant.

* [Oracle Instant Client Basic Light](https://www.oracle.com/database/technologies/instant-client.html) 19.5, téléchargeable [ici en 64 bits](https://www.oracle.com/database/technologies/instant-client/winx64-64-downloads.html) et [là en 32 bits](https://www.oracle.com/database/technologies/instant-client/microsoft-windows-32-downloads.html).
