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

1. Dans le menu « Scan FME », créer un nouveau point d’entrée en cliquant sur « + Nouveau... » ;
2. Sélectionner le type « Base de données (PostGIS, Oracle, SQL Server) » ;
3. Nommer le point d’entrée.
4. Sélectionner le type de base de données dans la liste déroulante. ;
5. Saisir les paramètres de connexion ;
6. Sauvegarder.

    ![Nouveau point d'entrée de type base de donnée](/assets/new_DB_ready.png)

## Paramètres requis selon le type de base de données {#parameters}

Légende :

* X = requis
* \ = facultatif
* \- = désactivé

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
