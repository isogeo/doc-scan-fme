---
description: Notes de versions (changelog) du Scan FME Isogeo (client Windows)
---

# Notes de versions du service client Isogeo Worker {#versions_client}

Indépendant de la plateforme, le service est mis à jour automatiquement lorsque des anomalies sont remontées ou pour couvrir de nouveaux besoins identifiés (nouveaux formats par exemple). Attention, ne pas confondre avec les mises à jour concernant l'interface d'administration du scan à laquelle vous accédez via [https://app.isogeo.com/admin/isogeo-worker](https://app.isogeo.com/admin/isogeo-worker).

Vous pouvez facilement vérifier la version du service installée en ouvrant la page de détail du service en cliquant sur son nom depuis l'interface. Une note de version accompagne le service.

![Scan FME - Version du service](/assets/service_version.png)

## Versions valides {#valid}

### 2.6.1 (24 juin 2020)

* Correction d’un bug lors de l’étape “Recenser” affectant les bases de données comportant plusieurs centaines de couches

### 2.6.0 (17 juin 2020)

Voir [l'article de blog](https://www.isogeo.com/blog-et-actus/2020/06/16/Refonte-du-Scan-Isogeo-tour-d-horizon).

* Nouveau protocole de communication avec le serveur (ne nécessite plus l'ouverture d'un port)
* Introduction de la mise à jour automatique du service
* Configuration du service à partir de l’interface de gestion et prise en compte immédiate
* Remontée d’informations concernant l’environnement d’exécution
* Mise à jour vers Node.js 12.18.0
* Amélioration de la fiabilité du processus de scan
* Corrections diverses

_________

## Versions obsolètes {#deprecated}

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
