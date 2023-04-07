---
description: Créer un point d'entrée de type base de données (PostgreSQL, PostGIS, Oracle, Microsoft SQL Server) pour le Scan FME Isogeo
---

# Système de Gestion de Base de Données (SGBD) <i class="fa fa-database"></i> {#sgbd}

Indiquer les paramètres de connexion à la base de données et les instances / schémas à scanner.

## Caractéristiques et précisions {#precisions}

* les SGBD sont indépendants du système d'exploitation ;
* les bases de données dites "plates" ou "fichiers" sont considérées comme des fichiers (Esri FileGDB par exemple) ;
* les tables sans géométrie ne sont pas prises en compte ;
* une table visible depuis plusieurs chaînes de connexion n'est pas dupliquée.

## Ajouter un point d'entrée vers une base de donnée {#process}

Pour créer un point d’entrée « Base de données » :

1. Dans le menu « Scan FME », créer un nouveau point d’entrée en cliquant sur « + Créer » ;
2. Sélectionnez le type « Bases de données (PostGIS, Oracle, SQL Server) » ;
3. Renseigner les champs du point d'entrée répartis en quatre sections : Informations, Métadonnées, Inclusion de données, Exclusion de donnée ;
4. Enregistrer et créer le point d'entrée.

#### Informations {#add_informations}

Informations générales du point d'entrée. Les champs de cette partie doivent obligatoirement être renseignés afin de pouvoir enresgistrer et créer le point d'entrée.

1. Nommer le point d’entrée ;
2. Renseigner les paramètres de connexion à la base de données.

#### Métadonnées {#add_metadata}

La section "Métadonnées", permet de sélectionner les étiquettes à associer à toutes les fiches du point d'entrée. Les champs de cette section sont optionnels.

**NOTE** : Les métadonnées sélectionnées dans le point d'entrée seront ajoutées à toutes les fiches de ce dernier, même si elles sont ajoutées après le premier scan.

Sélectionner les métadonnées de la liste suivante à associer aux fiches de métadonnées :

* Catalogues : Tous les catalogues sur app.isogeo.com ;
* Thématiques : Seules les thématiques sélectionnées ;
* Thèmes INSPIRE : Tous les thèmes INSPIRE ;
* Mot-clés : La liste de mots-clés associés **OU** la liste restreinte de mots-clés.

L'ajout de nouvelles métadonnées se fait automatiquement lors d'un Scan.

#### Inclusion de données {#add_inclusions}

La section "Inclusion de données" permet la sélection des données du point d'entrée à scanner. Seules les données correspondant au critère d'inclusion seront scannées. Les champs de cette partie sont optionnels.

Renseigner les trois champs en fonction du besoin :

* Schémas : Ajouter le(s) schéma(s) à inclure ;
* Données : Ajouter la ou les données à inclure. Le nom de la données doit obligatoirement avoir la forme suivante : schéma.nom_de_table.

Il est possible, pour les trois types d'inclusion, d'importer une liste depuis un fichier CSV (cf. [Annexe sur le format du fichier CSV](appendices/csv.md)). Il est aussi possible de supprimer le contenu de chaque liste séparément.

#### Exclusion de données {#add_exclusions}

La section "Exclusion de données" permet la sélection des données du point d'entrée à ignorer par le Scan. Seules les données correspondant au critère d'exclusion seront scannées. Les champs de cette partie sont optionnels.

Renseigner les trois champs en fonction du besoin :

* Schémas : Ajouter le(s) schéma(s) à exclure ;
* Données : Ajouter la ou les données à exclure. Le nom de la données doit obligatoirement avoir la forme suivante : schéma.nom_de_table.

Il est possible, pour les trois types d'exclusion, d'importer une liste depuis un fichier CSV (cf. [Annexe sur le format du fichier CSV](appendices/csv.md)). Il est aussi possible de supprimer le contenu de chaque liste séparément.

## Paramètres requis selon le type de base de données {#parameters}

<!-- Légende :

* X = requis
* \ = facultatif
* \- = désactivé -->

| Champ                       | PostGIS | Oracle | SQL Server |
| --------------------------- | :-----: | :----: | :--------: |
| Nom                         | X       | X      | X          |
| Type                        | X       | X      | X          |
| Serveur                     | X       | X      | X          |
| Port                        | X       |        |            |
| Identifiant                 | X       | X      | X          |
| Mot de passe                | X       | X      | X          |
| Nom de la base de données   | X       |        | X          |
<!-- | Nom de l'instance           | -       |        |            |
| Version transactionnelle    | -       |        |            | -->

### Cas spécifique des bases Oracle

Pour les bases Oracle, il n'est pas nécessaire de renseigner le port et le nom de la base de donnée. 
En revanche, vous pouvez indiquer dans le champs `Serveur`, soit l'hôte du serveur (ip ou domaine), soit le nom de l'instance configurée dans le fichier `tnsnames.ora` selon la configuration de votre environnement.
Attention à ne pas basculer de l'un à l'autre en modifiant le champ `Serveur`. En effet, cela peut entrainer des doublons puisque le Scan considère qu'il ne s'agit pas de la même base de donnée. 