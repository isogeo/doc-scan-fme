---
description: Changelog des versions du plugin Isogeo pour QGIS
---

# Notes de versions


<!-- timeline -->

## 1.6.3 {#version163}

<br> Publiée le 1er février 2019 :

> [Consulter la fiche de version sur Github.](https://github.com/isogeo/isogeo-scan-fme/milestone/8?closed=1)

* correction d'un problème bloquant l'installation [#165](https://github.com/isogeo/isogeo-scan-fme/issues/165)
* correction d'un problème bloquant l'ajout de données raster [#166](https://github.com/isogeo/isogeo-scan-fme/issues/166)

<!-- /timeline -->

<!-- timeline -->

## 1.6.2 {#version162}

<br> Publiée le 30 novembre 2018 :

* amélioration du système de cache [#135](https://github.com/isogeo/isogeo-scan-fme/issues/135)

<!-- /timeline -->

<!-- timeline -->

## 1.6.1 {#version161}

<br> Publiée le 1er août 2018 :

> [Consulter la fiche de version sur Github.](https://github.com/isogeo/isogeo-scan-fme/milestone/7?closed=1)

* amélioration du rapport d'anomalie [#139](https://github.com/isogeo/isogeo-scan-fme/issues/139#issuecomment-405258056)
* l'authentification à l'API Isogeo est désormais capable de gérer d'autres isntances que celle de la plateforme Isogeo. Requis pour une installation [_on-premises_](https://fr.wikipedia.org/wiki/Auto-h%C3%A9bergement_(Internet)). [#149](https://github.com/isogeo/isogeo-scan-fme/issues/149)
* corrections d'anomalies mineures :
    - depuis la version précédente, certaines icônes ne s'affichaient pas dans la fiche de métadonnées [#147](https://github.com/isogeo/isogeo-scan-fme/issues/147 et [#148](https://github.com/isogeo/isogeo-scan-fme/issues/148))
    - une erreur pouvait intervenir dans certains cas de chargement de données fichiers [#129](https://github.com/isogeo/isogeo-scan-fme/issues/129)
    - des fenêtres d'information à l'utilisateur ne fonctionnaient pas
    - le fond de carte d'une métadonnée détaillée ne s'affichait [plus #150](https://github.com/isogeo/isogeo-scan-fme/issues/150)

<!-- /timeline -->

<!-- timeline -->

## 1.6 {#version16}

<br> Publiée le 30 avril 2018 :

> [Consulter la fiche de version sur Github.](https://github.com/isogeo/isogeo-scan-fme/milestone/6?closed=1)

* ajout des filtres contacts et licences
* ajout du filtre sur toutes les données (vecteur ET raster) dans le type
* ajout de la possibilité d'ajouter les services Esri (Feature et Map) documentés sur Isogeo
* gestion de l'ordre des formats à ajouter
* finalisation de la fenêtre d'authentification
* remaniement de l'interface de recherche
* corrections d'anomalies mineures

<!-- /timeline -->

<!-- timeline -->

## 1.5 {#version15}

<br> Publiée le 30 mai 2017 :

> [Consulter la fiche de version sur Github.](https://github.com/isogeo/isogeo-scan-fme/milestone/5?closed=1)

* refonte de la fiche de métadonnées : informations complètes, présentation en onglets, design.
* gestion des nouvelles métadonnées de service Isogeo : appel du _GetCapabilities_ pour les informations complémentaires, optimisation de la construction d'URL d'ajout à QGIS, gestion des espaces de nommage
* gestion automatique des vues PostgreSQL
* remplissage des informations sur la couche dans QGIS à partir des métadonnées Isogeo
* réduction de la liste de résultats à 10 éléments (au lieu de 15)
* corrections d'anomalies : recherche par SRS, problèmes dans l'ajout de services, informations sur les partages dans l'onglet des paramètres.

<!-- /timeline -->
<!-- timeline -->

## 1.2 {#version12}

<br> Publiée le 28 décembre 2016 :

> [Consulter la fiche de version sur Github.](https://github.com/isogeo/isogeo-scan-fme/milestone/2?closed=1)

* ajout d'une fenêtre "A propos" avec les crédits
* ajout de messages d'informations temporaires dans QGIS
* ajout de la valeur "Aucun" aux filtres
* refonte de l'onglet des paramètres
* traduction de tous les intitulés dans la fiche de métadonnées détaillée
* support de QGIS 2.16
* documentation utilisateur
* corrections diverses : ajout WMS, plantages, encodage, barres de progression...

<!-- /timeline -->
<!-- timeline -->

## 1.0 {#version10}

<br> Publiée le 1er octobre 2016 :

> [Consulter la fiche de version sur Github.](https://github.com/isogeo/isogeo-scan-fme/milestone/1?closed=1)

* produit minimum atteint ;
* socle fonctionnel de base : recherche textuelle, filtres dynamiques, recherche géographique, affichage des résultats, ajout des données, fiche de métadonnées minimaliste, recherches rapides, etc.

<!-- /timeline -->
