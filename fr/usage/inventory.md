---
description: Fonctionnement global du Scan FME (Isogeo)
---

# Fonctionnement global du Scan FME {#operation}

Le Scan s'appuie FME pour parcourir les données et nécessite donc quune licence soit disponible durant le processus. Par défaut, le scan lance jusquà 3 instances de FME en parallèle, avec une seule licence utilisée (voir [Configuration Avancée - Paralléliser](/configuration/multiprocessus.html)).

Chaque instance soccupe dune action associée à une donnée : par exemple *signer GEOFLA.DEPARTEMENTS* ou *documenter GEOFLA.COMMUNES*. Une file dattente (indépendante des points dentrée) démarre une nouvelle instance dès quune se termine.

La licence de FME utilisée est de nouveau disponible pour dautres usages une fois le scan terminé.

![Tour dhorizon de linterface du Scan](/assets/tour_GeoFLA_2016-07-15.gif "Tour dhorizon de linterface de gestion du Scan")

## Processus {#process}

1. Cliquer sur le bouton « Scanner » en regard du point d’entrée choisi. La liste des requêtes s’affiche.

    ![Les requêtes dun point dentrée](/assets/EntryPoint_Requests.png "Afficher lhistorique des requêtes effectuées sur un point dentrée")

2. Cliquer sur la ligne d’une requête en cours pour visualiser le scan.

    ![Déroulement dun scan](/assets/ProcessLive_GeoFLA_2014-12-26.gif "Le processus de scan à loeuvre")

3. L’opération de scan se déroule en 3 phases :

    1. Recenser : le scan dresse la liste des données ;
    2. Signer : le scan signe toutes les données qu’il a recensées de façon à marquer les données au moment du scan et pouvoir en déduire si la donnée a déjà été scannée ou pas auparavant ou modifiée depuis le dernier scan ;
    3. Documenter : le scan crée les fiches pour les données nouvellement détectées ou met à jour les fiches des données modifiées.

    ![Les formats scannés automatiquement](/assets/PostGIS_requete_annot.png "Chercher les données dans Isogeo")

4. Une fois terminé, le scan vous indique :

    * La liste complète des données recensées. Dans cette liste, chaque donnée est caractérisée par un identifiant unique, son nom, son emplacement, son format et son statut (nouveau, modifiée, déplacée, inchangée, erreur). Vous pouvez trier ce tableau ;
    * La liste des données sans entités géographiques ;
    * La liste des données en doublons ;

La liste des données sans entités géographiques et celle des doublons sont informatives. Elles vous permettent d’agir au sein de votre base de données.

La liste complète des données recensées pendant le scan vous permet d’identifier :

* Les nouvelles données ajoutées à votre inventaire ;
* Les données inchangées depuis le dernier scan ;
* Les données modifiées depuis le dernier scan ;
* Les données déplacées depuis le dernier scan.

Allez dans l’inventaire pour découvrir ces données et parcourir leurs métadonnées.

## Cas particuliers {#cases}

* Le renommage un point dentrée nest pas possible aujourdhui. Il faut nécessairement le supprimer et en re-créer un ;

* Pour les bases de données, FME sappuie sur lutilisateur que vous configurez. Une table visible à partir de plusieurs points dentrée par plusieurs utilisateurs (chaînes de connexion différentes) ne sera pas dupliquée.

* Si vous copiez une donnée sans changer le nom de fichier, le scan indiquera quil a détecté un doublon mais créera quand même une nouvelle fiche ;

* Les attributs dont les noms commencent par `fme_`, `apic_` et `gml_` sont considérés comme des champs techniques spécifiques à des outils (comme FME) et ne sont pas remontés.
