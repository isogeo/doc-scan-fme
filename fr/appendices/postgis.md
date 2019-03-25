# Configurer les schémas PostgreSQL visibles par le Scan

Lors du scan d&apos;un point d&apos;entrée de type base de données, c&apos;est l&apos;utilisateur configuré qui détermine quelles tables et vues seront scannées dans l&apos;instance (pour Oracle) ou dans la base de données (pour PostgreSQL et MS SQL Server) indiquée.

Par défaut dans PostgreSQL et donc dans PostGIS, le schéma public est créé dans chaque nouvelle base de données et tout utilisateur pouvant s&apos;y connecter voit ce schéma. Les bonnes pratiques incitent à ne pas stocker de données dans ce schéma, mais de créer plusieurs schémas sur lesquels sont affinés les droits des utilisateurs ou groupes d&apos;utilisateurs, garantissant une meilleure granularité des usages et une isolation de la sécurité.

FME s&apos;appuie sur les droits et le chemin de parcours (*search_path*) pour établir sa connexion à une base PostGIS. Parfois, la base n&apos;est pas correctement configurée.

Pour que le Scan FME puisse analyser les tables d&apos;un schéma, il faut donc que :
* l&apos;utilisateur configuré ait les droit en lecture sur les tables ;
* le chemin du parcours de l&apos;utilisateur contienne les schémas contenant les tables.

## Démonstration et commandes

Prenons l&apos;exemple d&apos;une base de données PostgreSQL 9.3 avec une base PostGIS 2.1.3 intitulée *geofla* dont laquelle sont stockées les limites administratives du [produit idoine de l&apos;IGN France](http://professionnels.ign.fr/geofla) et structurée en 9 schémas dont 6 correspondant à la métropole et chaque DOM, l&apos;un (*global*) la fusion de l&apos;ensemble et les 2 derniers étant les schémas inhérents au SGBD et ses extensions (*public* et *topology*).

L&apos;objectif est de scanner les tables des 6 schémas de données avec l&apos;utilisateur *isogeo_demo* appartenant au groupe *isogeo_editor*.

![PGAdmin 3 - Structure GeoFLA](/assets/annex_scanPostGIS_db_geofla.png "Structure de la base de données GeoFLA dans PgAdmin")

### 1. Configurer le point d&apos;entrée

Suivre [les indications données ici](/features/scan_fme/scanFME_new_db.html), afin d&apos;obtenir quelque chose de similaire à cela :

![APP - Point d&apos;entrée PostGIS](/assets/annex_scanPostGIS_entryPoint_geofla.png "Point d&apos;entrée configuré dans Isogeo")

### 2. Constater que rien ne s&apos;affiche

Si on lance le scan, on s&apos;aperçoit que la seule table remontée est *public.raster_columns* qui est une table système de l&apos;extension PostGIS. Elle est en erreur car ne contenant aucune entité géographique.

![APP - 1er scan du point d&apos;entrée](/assets/annex_scanPostGIS_scan0.png "Premier scan : aucune table ne semble accessible")

### 3. Vérifier que l&apos;utilisateur accède bien aux tables

Il faut d&apos;abord s&apos;assurer de ce que "voit" l&apos;utilisateur utilisé, en passant par votre console psql (ou via une interface graphique comme pgAdmin) :
```sql
GRANT USAGE ON SCHEMA guadeloupe, guyane, lareunion TO isogeo_editor;
GRANT USAGE ON SCHEMA guadeloupe, guyane, lareunion TO isogeo_demo;
GRANT SELECT ON ALL TABLES IN SCHEMA guadeloupe, guyane, lareunion to isogeo_demo;
```
En passant par QGIS, on peut constater que l&apos;utilisateur *isogeo_demo* a accès aux tables des schémas *guadeloupe*, *guyane* et *lareunion*. Noter donc que tous les logiciels ne se connectent pas de la même façon à une base PostgreSQL. Ainsi, QGIS ne nécessite pas que le *search_path* soit configuré. FME, si.

![QGIS - Point d&apos;entrée PostGIS](/assets/annex_scanPostGIS_grant_user_ok_qgis.png "La connexion avec isogeo_demo via QGIS fonctionne")

### 4. Changer le chemin de parcours de l&apos;utilisateur

Pour changer le *search_path* il faut exécuter :
```sql
ALTER ROLE isogeo_demo IN DATABASE geofla SET search_path TO &apos;$user&apos;, &apos;public&apos;, &apos;guadeloupe&apos;;
```
En lançant à nouveau le scan, on constate alors que les tables du schéma *guadeloupe*, **et seulement de celui-ci**, sont bien scannées :

![APP - 2ème scan du point d&apos;entrée](/assets/annex_scanPostGIS_scan1_guadeloupe.png "Le schéma guadeloupe est bien scanné")

### 5. Conséquences et illustrations

La prise en compte de cette finesse de configuration de la base de données permet en fait d&apos;affiner la démarche de catalogage en choisissant une bonne granularité sur les points d&apos;entrée au moment de scanner.<br \>
Par ailleurs on peut voir que les variations sur le *search_path*  sur un même point d&apos;entrée ne changent rien à la "mémoire" du Scan FME :

Uniquement le schéma *guyane* :
```sql
ALTER ROLE isogeo_demo IN DATABASE geofla SET search_path TO &apos;$user&apos;, &apos;public&apos;, &apos;guyane&apos;;
```

![APP - 3ème scan du point d&apos;entrée](/assets/annex_scanPostGIS_scan2_guyane.png "Le schéma guyane est bien scanné")

Uniquement le schéma *lareunion* :
```sql
ALTER ROLE isogeo_demo IN DATABASE geofla SET search_path TO &apos;$user&apos;, &apos;public&apos;, &apos;lareunion&apos;;
```

![APP - 4ème scan du point d&apos;entrée](/assets/annex_scanPostGIS_scan3_lareunion.png "Le schéma lareunion est bien scanné")

Les 3 schémas :
```sql
ALTER ROLE isogeo_demo IN DATABASE geofla SET search_path TO &apos;$user&apos;, &apos;public&apos;, &apos;guadeloupe&apos;, &apos;guyane&apos;, &apos;lareunion&apos;;
```

![APP - 5ème scan du point d&apos;entrée](/assets/annex_scanPostGIS_scan4_all.png "Les 3 schémas sont bien scannés")

## Résumé des commandes

Si on avait voulu scanner l&apos;ensemble des 6 schémas dans lesquels sont stockées les données, on aurait fait :

```sql
/* Granting access to role and rolegroup to wanted schemas*/
GRANT USAGE ON SCHEMA guadeloupe, guyane, lareunion, martinique, mayotte, metropole TO isogeo_editor;
GRANT USAGE ON SCHEMA guadeloupe, guyane, lareunion, martinique, mayotte, metropole TO isogeo_demo;
GRANT SELECT ON ALL TABLES IN SCHEMA guadeloupe, guyane, lareunion, martinique, mayotte, metropole to isogeo_demo;

/* Setting the search_path with the wanted schemas */
ALTER ROLE isogeo_demo IN DATABASE geofla SET search_path TO &apos;$user&apos;, &apos;public&apos;, &apos;guadeloupe&apos;, &apos;guyane&apos;, &apos;lareunion&apos;, &apos;martinique&apos;, &apos;mayotte&apos;, &apos;metropole&apos;;
```

### Précisions complémentaires

* le chemin du parcours de l&apos;utilisateur doit obligatoirement contenir *public*, sinon FME n&apos;y parviendra pas ;
* le *$user* correspond à la table de l&apos;utilisateur. Facultatif. ;
* il est possible de réinitialiser le search_path d&apos;un utilisateur à la configuration par défaut du SGBD :
    ```sql
    ALTER USER isogeo_demo RESET search_path;
    ```
* pour consulater le search_path d&apos;un utilisateur, se connecter à une base de données avec celui-ci et exécuter :
    ```sql
    show search_path;
    ```

## Ressources

* Dans la documentation officelle de PostgreSQL (version 9.3) : [Chemin de parcours des schémas](http://docs.postgresql.fr/9.3/ddl-schemas.html#ddl-schemas-path) ;
* Dans les forums de FME (EN) :
    * [In the Postgis/Postgres reader tables from a different schema don&apos;t show up or it doesn&apos;t appear to display the full list of tables](https://knowledge.safe.com/articles/480/in-the-postgispostgres-reader-tables-from-a-differ.html) ;
    * [Setting Postgis Metadata Table Permissions](https://knowledge.safe.com/articles/420/setting-postgis-metadata-table-permissions.html).
