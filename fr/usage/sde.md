# ArcSDE <i class="fa fa-database"></i>

## Caractéristiques et précisions

* les SGBD sont indépendants du système d&apos;exploitation ;
* les bases de données dites "plates" ou "fichiers" sont considérées comme telles (Esri FileGDB par exemple) ;
* les tables sans géométrie ne sont pas prises en compte ;
* une table visible depuis plusieurs chaînes de connexion n&apos;est pas dupliquée.

## Démarche globale

Pour créer un point d’entrée « SDE » :

1. Dans le menu « Scan FME », créer un nouveau point d’entrée en cliquant sur « + Nouveau » ;
2. Sélectionner le type « Base de données » ;
3. Nommer le point d’entrée. Exemple : Base de références ;
4. Sélectionner le type de base de données sur lequel est installée la cartouche spatial SDE ;
5. Dans `Paramètres de la geodatabase ESRI`, cocher `Oui` 
6. Indiquer le chemin vers le fichier de connexion (.sde)
7. Sauvegarder.

    ![Nouveau point d&apos;entrée base](/assets/scanFME_new_DB_ready.png "Le nouveau point d&apos;entrée est prêt à être scanné")
