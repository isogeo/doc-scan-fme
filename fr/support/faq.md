# Question et erreurs fréquentes {#questions_errors}

De notre expérience d'années de support, dans la plupart des cas les soucis sont résolus en vérifiant de nouveau [les prérequis](/prerequisites.md) puis en redémarrant le service. Sinon cette page peut peut-être répondre à votre problème, avant d'écrire au [support du Scan](support.html).

## Du côté de l'installation {#installation}

Si le message suivant s'affiche, veuillez vérifier [les prérequis](/prerequisites.md), en particulier [les droits de l'utilisateur configuré](/installation/server.md#user) pour lancer le service.

![Service non démarré](/assets/install_errors_ServiceDoNotStart.png "Le service na pas démarré")

----

## Du côté de l'interface {#interface}

### Problème d'authentification {#scan_err_ui_auth}

Après s'être authentifié sur l'interface du Scan FME, il arrive que l'interface du scan ne s'affiche pas. Il s'agit d'un problème qui peut intervenir lors de multiples authentifications à Isogeo dans différents onglets.

Pour résoudre le problème, cliquer sur https://scan.isogeo.com/api/logout puis réessayez.

### Impossible d'accéder au chemin spécifié {#scan_err_ui_unreachable}

Si l'un des messages ci-dessous s'affiche, c'est qu'il y a un problème avec les paramètres d'accès aux données entrées dans le point d'entrée : chemin, schéma, base de données, droits utilisateur...

![Echec du scan : problème d'accès](/assets/scan_errors_UnableToAccessEntryPoint.png)
----

## Cas particuliers connus {#scan_known_cases}

### Shapefile supérieur à 2 Go {#scan_err_shp_too_big}

FME ne lit pas les shapefiles dont la taille de chaque composant (.shp / .dbf / .shx ...) dépasse les 2 Go, comme indiqué dans [la base de connaissance officielle](https://knowledge.safe.com/articles/772/fme-and-esri-arcgis-troubleshooting-guide.html) :

>  Note: Shape datasets larger than 2GB are considered invalid and will cause errors when opened in other applications.

Il s'agit d'ailleurs d'une limite inhérente au format, qu'Esri précise dans http://support.esri.com/technical-article/000010813[](http://support.esri.com/technical-article/000010813).

<!-- ### Donnée géographique corrompue ou incohérente {#scan_err_corrupted_data}

Si un jeu de données contient un objet sans géométrie, la donnée ne peut être lue jusqu'au bout par le Scan FME. Elle est donc indiquée dans la colonne erreur du détail de la requête du Scan avec la mention "Impossible de lire la donnée".

Dans le fichier LOG, lerreur intervient sur létape "LookUp". Exemple tiré dune table PostGIS où le nombre denregistrement (lignes) était incohérent par rapport au nombre dobjets géométriques liés :

```json
{"worker":"wk-d864517e","level":"info","message":"(etl) Start new fme script from queue with options :  [ C:\\\\PROGRA~1\\\\Isogeo\\\\ISOGEO~1\\\\scripts\\\\lookup-postgis.fmw,\n  --OUTPUT_JSON,\n  C:\\\\PROGRA~1\\\\Isogeo\\\\ISOGEO~1\\\\tmp\\\\lookup-gC9aIjzL6,\n  --LOG_FILE,\n  C:\\\\PROGRA~1\\\\Isogeo\\\\ISOGEO~1\\\\tmp\\\\log-UUOBAvNXz,\n  --USERNAME,\n  isogeo,\n  --PASSWORD,\n  modepassepasse,\n  --SOURCE,\n  bdgeo_prod,\n  --HOST,\n  192.168.1.1,\n  --PORT,\n  5432,\n  --FEATURE_TYPES,\n  schema.dataset ]","timestamp":"2017-12-14T16:14:30.604Z"}
``` -->

### Mauvais nombre d'entités géographiques détecté (voire doublé) {#scan_err_featureCount}

#### Constat

Après un Scan, le nombre d'entités détecté et reporté dans les métadonnées ne correspond pas à celui du jeu de données (voire est doublé).

#### Problème

Le Scan a été lancé avec une version de FME non compatible (FME 2017).

#### Solution

Installer FME 2016.1 ou FME 2018 comme indiqué dans [les prérequis](/prerequisites.md), puis redémarrer le service.

### Le nom de la donnée est le type de géométrie {#scan_err_badName}

#### Constat {#scan_err_badName_obs}

Après un Scan, le nom du jeu de données (et donc son titre si la métadonnée est nouvelle) est le type de géométrie (point...) au lieu du nom du fichier/de la table.

#### Problème {#scan_err_badName_diagnostic}

Le Scan a été lancé avec une version de FME non compatible (FME 2017).

#### Solution {#scan_err_badName_solve}

Installer FME 2016.1 ou FME 2018 comme indiqué dans [les prérequis](/prerequisites.md), puis redémarrer le service.

----

### Le service refuse de démarrer (commande interne non reconnue) {#batch_error_file}

#### Constat {#scan_err_bad_filepath_obs}

![Installation impossible](/assets/support_batch_error_bad_file_path.png)

#### Problème {#scan_err_bad_filepath_diagnostic}

Le problème provient d'une impossibilité de résoudre le chemin Windows avec des espaces lorsque c'est le disque D (alors que ça fonctionne sur le disque C:).

#### Solution {#scan_err_bad_filepath_solve}

S'assurer qu'il n'y a aucun espace ou caractère spécial dans le chemin du dossier d'installation du service de Scan.
