## Installation de FME Desktop

FME Desktop doit être installé et parfaitement configuré pour accéder et manipuler vos données géographiques. Points de vérification :

* édition de la licence (Professionnal ou Esri Edition pour ArcSDE)  ;
* jeton de licence FME disponible au moment du scan ;
* architecture 32 ou 64 bits ;
* plugins spécifiques.

À ce jour, les versions de FME supportées sont :

* de FME Desktop 2013 SP4 ;
* à FME Desktop 2016 SP1.

Ainsi que les Service Pack associés.

Pour télécharger FME :

* la dernière version compatible [en 32 bits](https://s3.amazonaws.com/downloads.safe.com/fme/2016/fme-desktop-b16717-win-x86.msi) ou [en 64 bits](https://s3.amazonaws.com/downloads.safe.com/fme/2016/fme-desktop-b16717-win-x64.msi) ;
* une [ancienne version spécifique](https://www.safe.com/support/support-resources/fme-downloads/archived/).

Pour plus d’informations, veuillez contacter votre distributeur FME.

### Cas spécifique pour les connexions Esri ArcSDE

Pour des questions dinteropérabilité entre FME et Esri, il faut être particulièrement vigilant sur les prérequis à installer pour pouvoir scanner correctement les schémas ArcSDE.

1. Tout dabord, il faut **la version 32 bits de FME** et si possible lédition Esri
2. Ensuite :
    * soit ArcGIS Desktop 32 bits sur la même machine avec une licence disponible pendant toute la durée du Scan - méthode recommandée ;
    * soit installer les librairies SDE sur la machine où est installée votre FME ([voir cet article](https://knowledge.safe.com/articles/358/arcsde-libraries-required-for-the-esri-arcsde-sde3.html)) - méthode plus complexe.
3. Si ArcGIS est en licence flottante liée à un serveur de licences distant, ajouter la variable denvironnement `ARCGIS_LICENCE_FILE` (voir [la doc Esri](http://resources.arcgis.com/fr/help/install-guides/license-manager/10.1/index.html#/Defining_port_host_to_one_or_more_license_servers/00790000000t000000/)) avec pour valeur le port et ladresse de votre serveur de licence (information située dans ArcGIS Administrator) :

    ![Scan - ArcGIS SDE license](/assets/install_SDE_env_var_arcgis_licensing.png "Variable denvironnement pour le serveur de licence dArcGIS")

Pour aller plus loin :

* consulter la [matrice des formats et versions de FME](https://www.safe.com/fme/formats-matrix/#search=arcsde) ;
* consulter [larticle dédié [en]](https://knowledge.safe.com/articles/1517/notes-on-fme-and-esri-versions-and-compatibility.html) à ces questions dinteropérabilité sur le site de Safe, éditeur de FME.
* si vous utilisez une [version dArcGIS qui nest plus supportée](http://support.esri.com/other-resources/product-life-cycle) par Esri, [consulter larticle dédié](https://knowledge.safe.com/articles/22886/fme-compatibility-for-retired-esri-software.html) ;
* si vous utilisez Direct Connect, [consulter cet article](https://knowledge.safe.com/articles/227/how-do-i-connect-to-my-arcsde-geodatabase-using-di.html).

### Oracle

Pour les bases de données Oracle, penser à installer le client sur la même machine que FME.
