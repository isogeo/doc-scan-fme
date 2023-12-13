---
description: Notes de versions (changelog) du Scan FME Isogeo (client Windows)
---

# Notes de versions du scan {#versions_client}

Les notes de version concernent l'interface, le serveur et le client du scan. 

## Client du scan

Indépendant de la plateforme, le service est mis à jour automatiquement lorsque des anomalies sont remontées ou pour couvrir de nouveaux besoins identifiés (nouveaux formats par exemple). Attention, ne pas confondre avec les mises à jour concernant l'interface d'administration du scan à laquelle vous accédez via [https://app.isogeo.com/admin/isogeo-worker](https://app.isogeo.com/admin/isogeo-worker).

Vous pouvez facilement vérifier la version du service installée en ouvrant la page de détail du service en cliquant sur son nom depuis l'interface. Une note de version accompagne le service.

![Scan FME - Version du service](/assets/service_version.png)

## Versions valides {#valid}

### Décembre 2023

**Version de l'interface :** 0.2.3

* Correctifs divers

**Version du serveur :** 4.1.1
**Version de l'interface :** 0.2.2

* Correctifs d'un cas particulier de listing

### Octobre 2023

**Version du serveur :** 4.0.14

* Meilleure gestion des suprresions de point d'entrée 

### Septembre 2023

**Version du serveur :** 4.0.13
**Version du client:** 3.3.3
**Version de l'interface :** 0.1.13

* Correctifs divers 

### Juin 2023

**Version du serveur :** 4.0.12
**Version du client:** 3.3.1
**Version de l'interface :** 0.1.12

* Amélioration de la récupération des fiches de métadonnées en cas d'erreur
* Mise à jour des liens d'aide en ligne
* Corrections de dysfonctionnements

**Version du serveur :** 4.0.11

* Corrections de dysfonctionnements

### Mai 2023

**Version du serveur :** 4.0.10
**Version du client :** 3.3.0

* Corrections de dysfonctionnements dans l'interface
* Meilleure gestion des fonctionnalités optionnelles 

### Avril 2023

* Ajout de la possibilité d'importer grâce à un .csv les inclusions et exclusions
* Modification des statistiques d'une requête
* Corrections de bugs

### Mars 2023

**Version du serveur :** 4.0.9

* Compatibilité avec FME 2022
* Possibilité de définir des inclusions de données dans les points d'entrée

**Version du serveur :** 4.0.8

* Affichage du temps effectif des jobs
* Ajout de précisions dans les instructions de debugage
* Optimisations mineures de l'interface

### Janvier 2023

**Version du client :** 3.2.0

* Corrections de dysfonctionnements dans le client
* Suppression du client de mises à jour expérimentales
* Corrections des workbenches FME

### Décembre 2022

**Version du serveur :** 4.0.7

* Corrections de bugs dans le serveur

### Novembre 2022

**Version du serveur :** 4.0.6

* Corrections de bugs dans le serveur

### Octobre 2022

* Augmentation du nombre maximum d'instances simultanées de FME

### Août 2022

* Facilitation de l'ajout de catalogues à un point entrée
* Corrections de problèmes dans l'interface du scan 

### Juillet 2022

**Version client :** 3.1.0
**Version du serveur :** 4.0.5

* Mise à jour des exécutables de NodeJs
* Meilleure gestion des filegdb Esri
* Corrections de bugs dans les Workbenches FME
* Corrections de bugs dans le serveur

### Juin 2022

**Version du serveur :** 4.0.4

* Possibilité d'associer à partir d'un point d'entrée les champs suivants : thématiques de groupe, mots-clés Isogeo et thématiques Inspire
* Ajout automatique des nouvelles métadonnées d'un point d'entrée à toutes les données lors d'un scan
* Synchronisation des chemins et des noms modifiés dès leur détection
* Corrections de bugs dans l'API du scan
* Améliorations de l'interface graphique

### Mars 2022

* Ajout d'instructions de débugage lors d'une erreur du scan
* Ajout d'informations statistiques sur la requête
* Améliorations diverses de l'interface

### Février 2022

**Version du client :** 3.0.0

**Version du serveur :** 4.0.3

- Possibilité de scanner des données tabulaires non géographiques au format PostGIS, Oracle Spatial ou Esri Entrerprise Geodatabase
- Meilleure gestion du passage de FME 2018 à une version supérieure
- Mise en place d'un mode permettant de garder les fichiers temporaires de FME dans le client
- Récupération d'informations sur le worker dans le serveur et l'interface
- Mises à jour graphiques variées (Modification de l'entête, warnings supplémentaires, ...)
- Corrections de bugs dans les Workbenches FME et dans l'API du Scan

### 21 octobre 2021

**Version du client :** 2.10.0

**Version du serveur :** 4.0.2

- Prise en compte des vues matérialisées PostGIS
- Possibilité de supprimer une requête
- Ajout d'informations sur les données en cours de traitement pour un suivi plus détaillé de l'avancement du Scan
- Ajustements mineurs de l'interface graphique (tri des points d'entrée, ajout de liens vers l'aide en ligne, affichage des erreurs ...)
- Correction de bugs dans les Workbenches FME et dans l'API du Scan

### Août 2021

**Version du client :** 2.9.1

- Prise en charge du format geojson `.geojson`

### 22 avril 2021

**Version du client :** Version 2.9.0

**Version du serveur :** 4.0.0

- Réécriture significative du gestionnaire de tâches
- Ajout d’un mécanisme “heartbeat” pour notifier la plateforme qu’une tâche est toujours en cours
- Amélioration de l’auto-nettoyage des fichiers temporaires
- Amélioration de la prise en charge ESRI GDB

### 9 mars 2021

**Version du client :** 2.8.1

- Correction de la stratégie de mise à jour automatique

### 9 mars 2021

**Version du client :** Version 2.8.0

- Meilleure détection des processus FME en erreur
- Amélioration de la stabilité du client Isogeo
- Ajout d'une fonctionnalité de redémarrage à distance du client Isogeo

### 9 septembre 2020

**Version du client :** Version 2.7.0

- Support des proxy HTTP/HTTPS côté client

### 24 juin 2020

**Version du client :** Version 2.6.1

* Correction d’un bug lors de l’étape “Recenser” affectant les bases de données comportant plusieurs centaines de couches

### 17 juin 2020

**Version du client :** Version 2.6.0

Voir [l'article de blog](https://www.isogeo.com/blog-et-actus/2020/06/16/Refonte-du-Scan-Isogeo-tour-d-horizon).

* Nouveau protocole de communication avec le serveur (ne nécessite plus l'ouverture d'un port)
* Introduction de la mise à jour automatique du service
* Configuration du service à partir de l’interface de gestion et prise en compte immédiate
* Remontée d’informations concernant l’environnement d’exécution
* Mise à jour vers Node.js 12.18.0
* Amélioration de la fiabilité du processus de scan
* Corrections diverses

_________

## Versions client obsolètes {#deprecated}

### 2.1.0

Voir [la lettre d'informations](http://eepurl.com/b8uYqb).

* Format XYZ
* Format SpatiaLite
* Format GML
* Scripts compatibles avec FME 2016 (toutes les données déjà scannées avec une version antérieure de FME sont considérées comme modifiées)
* Changement des adresses IP de destination

### 2.0.1

* Nouvelle signature permettant de détecter le renommage et le déplacement d’une donnée.
* Prise en compte du SRS pour tous les formats
* Nouvelle option permettant de forcer l’utilisation du script Esri Edition pour le format ArcSDE
* (Fix) Scan des formats raster (script lookup-raster.fmw défaillant)
* (Fix) non prise en compte de certaines géométries CAO/DAO

### 1.3.4

* Format LAS
* (Fix) Un scan continue même si le service n’a pas pu lire un dossier
* MAJ des dépendances

### 1.3.3

* (Fix) Calcul des enveloppes même si le système de coordonnées n’est pas reconnu (valeur *_FME_0*)

### 1.3.2

* Nouvelle version de [NSSM](http://nssm.cc/) (utilisé pour gérer le service Windows)
* (Fix) Désinstallation du service sur une machine 32 bits

### 1.3.1

* (Fix) Lecture du format ArcSDE sous Oracle.

### 1.3.0

* (Fix) Remonte les couches qui ne possèdent pas d’attribut ;
* Amélioration de la lecture du format KML/KMZ ;
* Amélioration de la lecture du format GPx ;
* Suppression du scan de requêtes SQL pour Créteil ;
* Scan de tables sans géométrie pour Créteil.

### 1.2.0

* Format Apic ASC

### 1.1.1

* Format GPx ;
* Format PNG.

### 1.1.0

* Scan de requêtes SQL pour Créteil / Plaine Centrale.

### 1.0.24

* Format KML/KMZ.

### 1.0.23

* Suppression des tables remontées en doublon par FME.

### 1.0.21

* Possibilité d’arrêter une requête.

> Au-delà de cette ligne, les services sont considérés comme obsolètes et le voyant s'affiche en orange.

![Scan FME - version obsolète](/assets/service_version_obsolete.png "Service obsolète")

### 1.0.20

* Format ESRI Grid (.asc) ;
* Format JPEG (.jpg et .jpeg).

### 1.0.19

* Amélioration du temps de calcul de la signature via FME (données marquées comme modifiées la première fois) ;
* Remontée des erreurs FME pour améliorer l’efficacité du support.

### 1.0.18

* Prise en compte du reader SDE30 de FME permettant de lire les bases ArcSDE avec la licence Professionnal ;
* Remonte des informations plus pertinentes pour les données CAO (les informations d’une seule couche étaient remontées).

### 1.0.17

* Ajout des bonnes versions 32 bits et 64 bits de NSSM.

### 1.0.16

* Version plus récente de NSSM.
