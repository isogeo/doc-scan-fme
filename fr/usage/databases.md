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
2. Sélectionner le type de point d'entrée « Base de données (PostGIS, Oracle, SQL Server) » ;
3. Nommer le point d’entrée ;
4. Sélectionner le type de base de données dans la liste déroulante ;
5. Saisir les paramètres de connexion ;
6. Choisir dans quel(s) catalogue(s) vous souhaitez ajouter automatiquement les nouvelles données scannées en le(s) sélectionnant (en général 1 catalogue de suivi et 1 catalogue thématique)
7. Si besoin, ajouter des schémas ou des tables à exclure.
8. Sauvegarder.

    ![Nouveau point d'entrée de type base de donnée](/assets/new_DB_ready.png)

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