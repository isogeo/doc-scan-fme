---
description: Fonctionnement global du Scan FME (Isogeo)
---

# Fonctionnement global du Scan FME {#operation}

Le Scan s'appuie sur FME pour parcourir les données et nécessite donc qu'une licence soit disponible durant le processus. Par défaut, le scan lance jusqu'à 3 instances de FME en parallèle, avec une seule licence utilisée (voir [Configuration du service](/configuration/configuration.md#scan_concurrency)).

Chaque instance s'occupe d'une action associée à une donnée : par exemple *signer GEOFLA.DEPARTEMENTS* ou *documenter GEOFLA.COMMUNES*. Une file d'attente (indépendante des points d'entrée) démarre une nouvelle instance dès qu'une se termine.

La licence de FME utilisée est de nouveau disponible pour d'autres usages une fois le scan terminé.

![Page d'accueil du Scan](/assets/interface_scan.png)

## Processus {#process}

1. Sélectionner un point d'entrée.

    ![Page d'un point d'entrée](/assets/entrypoint.png)

2. Cliquer sur le bouton « Scanner ». La requête lancée s’affiche.

    ![Requete d'un scan](/assets/request.png)

3. L’opération de scan se déroule en 3 phases :

    1. Recenser : le scan dresse la liste des données ;
    2. Signer : le scan signe toutes les données qu’il a recensées de façon à marquer les données au moment du scan et pouvoir en déduire si la donnée a déjà été scannée ou pas auparavant ou modifiée depuis le dernier scan ;
    3. Documenter : le scan crée les fiches pour les données nouvellement détectées ou met à jour les fiches des données modifiées.

4. Une fois terminé, le scan vous indique :

    * La liste complète des données recensées. Dans cette liste, chaque donnée est caractérisée par un identifiant unique, son nom, son emplacement, son format et son statut (nouveau, modifiée, déplacée, inchangée, erreur). 
    * Vous pouvez trier ce tableau et rechercher une table. Un système de pagination a également été mis en place.

La liste complète des données recensées pendant le scan vous permet d’identifier :

* Les nouvelles données ajoutées à votre inventaire ;
* Les données inchangées depuis le dernier scan ;
* Les données modifiées depuis le dernier scan ;
* Les données déplacées depuis le dernier scan.

Allez dans l’inventaire pour découvrir ces données et parcourir leurs métadonnées.

## Cas particuliers {#cases}

* Pour les bases de données, FME s'appuie sur l'utilisateur que vous configurez. Une table visible à partir de plusieurs points d'entrée par plusieurs utilisateurs (chaînes de connexion différentes) ne sera pas dupliquée.

* Si vous copiez une donnée sans changer le nom de fichier, le scan indiquera qu'il a détecté un doublon mais créera quand même une nouvelle fiche ;

* Les attributs dont les noms commencent par `fme_`, `apic_` et `gml_` sont considérés comme des champs techniques spécifiques à des outils (comme FME) et ne sont pas remontés.
