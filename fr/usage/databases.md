---
description: Créer un point d'entrée de type base de données (PostgreSQL, PostGIS, Oracle, Microsoft SQL Server) pour le Scan FME Isogeo
---

# Système de Gestion de Base de Données (SGBD) <i class="fa fa-database"></i> {#sgbd}

![Point dentrée SGBD](/assets/new_DB_btn.png "Sélecteur de type de point dentrée - Base de données")

Indiquer les paramètres de connexion à la base de données et les instances / schémas à scanner.

## Caractéristiques et précisions {#precisions}

* les SGBD sont indépendants du système dexploitation ;
* les bases de données dites "plates" ou "fichiers" sont considérées comme telles (Esri FileGDB par exemple) ;
* les tables sans géométrie ne sont pas prises en compte ;
* une table visible depuis plusieurs chaînes de connexion nest pas dupliquée.

## Démarche globale {#process}

Pour créer un point d’entrée « Base de données » :

1. Dans le menu « Scan FME », créer un nouveau point d’entrée en cliquant sur « + Nouveau » ;
2. Sélectionner le type « Base de données » ;
3. Nommer le point d’entrée. Exemple : Base de références ;
4. Sélectionner le type de base de données dans la liste déroulante. ;
5. Saisir les paramètres de connexion ;
6. Sauvegarder.

    ![Nouveau point dentrée base](/assets/new_DB_ready.png "Le nouveau point dentrée est prêt à être scanné")

## Paramètres requis selon le type de base de données {#parameters}

Légende :

* X = requis
* \ = facultatif
* \- = désactivé

| Champ                       | PostGIS | Oracle | SQL Server | + Esri (SDE) |
| --------------------------- | :-----: | :----: | :--------: | :----------------------: |
| Nom                         | X       | X      | X          | X                        |
| Type                        | X       | X      | X          | X                        |
| Serveur                     | X       | X      | X          |                          |
| Port                        | X       |        |            |                          |
| Identifiant                 | X       | X      | X          |                          |
| Mot de passe                | X       | X      | X          |                          |
| Nom de la base de données   | X       |        | X          |                          |
| Fichier de connexion (.sde) | -       |        |            | \                        |
| Nom de linstance           | -       |        |            | X                        |
| Version transactionnelle    | -       |        |            | X                        |
