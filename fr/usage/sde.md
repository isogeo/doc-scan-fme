## Système de Gestion de Base de Données (SGBD) <i class="fa fa-database"></i>

![Point d&apos;entrée SGBD](/assets/scanFME_new_DB_btn.png "Sélecteur de type de point d&apos;entrée - Base de données")

Indiquer les paramètres de connexion à la base de données et les instances / schémas à scanner.

### Caractéristiques et précisions

* les SGBD sont indépendants du système d&apos;exploitation ;
* les bases de données dites "plates" ou "fichiers" sont considérées comme telles (Esri FileGDB par exemple) ;
* les tables sans géométrie ne sont pas prises en compte ;
* une table visible depuis plusieurs chaînes de connexion n&apos;est pas dupliquée.

### Démarche globale

Pour créer un point d’entrée « Base de données » :

1. Dans le menu « Scan FME », créer un nouveau point d’entrée en cliquant sur « + Nouveau » ;
2. Sélectionner le type « Base de données » ;
3. Nommer le point d’entrée. Exemple : Base de références ;
4. Sélectionner le type de base de données dans la liste déroulante. ;
5. Saisir les paramètres de connexion ;
6. Sauvegarder.

    ![Nouveau point d&apos;entrée base](/assets/scanFME_new_DB_ready.png "Le nouveau point d&apos;entrée est prêt à être scanné")

### Paramètres requis selon le type de base de données

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
| Nom de l&apos;instance           | -       |        |            | X                        |
| Version transactionnelle    | -       |        |            | X                        |
