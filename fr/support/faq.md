# Question et erreurs fréquentes

De  notre expérience d&apos;années de support, dans la plupart des cas les soucis sont résolus en vérifiant de nouveau [les prérequis](prerequisites.html) puis en redémarrant le service. Sinon cette page peut peut-être répondre à votre problème, avant d&apos;écrire au [support du Scan](support.html).

## Du côté de l&apos;installation

Si le message suivant s&apos;affiche, veuillez vérifier [les prérequis](prerequisites.html), en particulier [les droits de l&apos;utilisateur configuré](prerequisites.html#compte-utilisateur) pour lancer le service.

![Service non démarré](/assets/scanFME/scanFME_install_errors_ServiceDoNotStart.png "Le service n&apos;a pas démarré")

____

## Du côté de l&apos;interface

### Problème d&apos;authentification \(Oups! Forbidden\) {#scan_err_ui_auth}

Après s&apos;être authentifié sur l&apos;interface du Scan FME, il arrive que le message ci-dessous s&apos;affiche. Il s&apos;agit d&apos;un problème qui peut intervenir lors de multiples authentifications à Isogeo dans différents onglets.

Pour résoudre le problème, cliquer sur https://daemons.isogeo.com/logout puis réessayez.

![Scan FME - Oups forbidden](/assets/scanFME/scanFME_error_forbidden.png "Scan FME - Problème d&apos;authentification \(Oups! Forbidden\)")

### Impossible d&apos;accéder au chemin spécifié {#scan_err_ui_unreachable}

Si l&apos;un des messages ci-dessous s&apos;affiche, c&apos;est qu&apos;il y a un problème avec les paramètres d&apos;accès aux données entrés dans le point d&apos;entrée : chemin, schém, base de données, droits utilisateur...

![Echec du scan](/assets/scanFME/scanFME_scan_errors_UnableToAccessEntryPoint.png "Impossible d&apos;accéder au chemin spécifié")

____

## Cas particuliers connus {#scan_known_cases}

### Shapefile supérieur à 2 Go {#scan_err_shp_too_big}

FME ne lit pas les shapefiles dont la taille de chaque composant (.shp / .dbf / .shx ...) dépasse les 2 Go, comme indiqué dans [la base de connaissance officielle](https://knowledge.safe.com/articles/772/fme-and-esri-arcgis-troubleshooting-guide.html) :

>  Note: Shape datasets larger than 2GB are considered invalid and will cause errors when opened in other applications.

Il s&apos;agit d&apos;ailleurs d&apos;une limite inhérente au format, qu&apos;Esri précise dans http://support.esri.com/technical-article/000010813[](http://support.esri.com/technical-article/000010813).

### Donnée géographique corrompue ou incohérente {#scan_err_corrupted_data}

Si un jeu de données contient un objet sans géomtrie, la donnée ne peut être lue jusqu&apos;au bout par le Scan FME. Elle est donc indiquée dans la colonne erreur du détail de la requête du Scan avec la mantion "Impossible de lire la donnée".

Dans le fichier LOG, l&apos;erreur intervient sur l&apos;étape "LookUp". Exemple tiré d&apos;une table PostGIS où le nombre d&apos;enregistrement (lignes) était incohérent par rapport au nombre d&apos;objets géométriques liés :

```json
{"worker":"wk-d864517e","level":"info","message":"(etl) Start new fme script from queue with options :  [ &apos;C:\\\\PROGRA~1\\\\Isogeo\\\\ISOGEO~1\\\\scripts\\\\lookup-postgis.fmw&apos;,\n  &apos;--OUTPUT_JSON&apos;,\n  &apos;C:\\\\PROGRA~1\\\\Isogeo\\\\ISOGEO~1\\\\tmp\\\\lookup-gC9aIjzL6&apos;,\n  &apos;--LOG_FILE&apos;,\n  &apos;C:\\\\PROGRA~1\\\\Isogeo\\\\ISOGEO~1\\\\tmp\\\\log-UUOBAvNXz&apos;,\n  &apos;--USERNAME&apos;,\n  &apos;isogeo&apos;,\n  &apos;--PASSWORD&apos;,\n  &apos;modepassepasse&apos;,\n  &apos;--SOURCE&apos;,\n  &apos;bdgeo_prod&apos;,\n  &apos;--HOST&apos;,\n  &apos;192.168.1.1&apos;,\n  &apos;--PORT&apos;,\n  5432,\n  &apos;--FEATURE_TYPES&apos;,\n  &apos;schema.dataset&apos; ]","timestamp":"2017-12-14T16:14:30.604Z"}
```

### Mauvais nombre d'entités géographiques détecté (voire doublé) {#scan_err_featureCount}

#### Constat

Après un Scan, le nombre d'entités détecté et reporté dans les métadonnées ne correspond pas à celui du jeu de données (voire est doublé).

#### Problème

Le Scan a été lancé avec une version de FME non compatible (FME 2018 ou 2017).

#### Solution

Installer FME 2016.1 comme indiqué dans [les prérequis](prerequisites.html), puis redémarrer le service.

### Le nom de la donnée est le type de géométrie {#scan_err_badName}

#### Constat {#scan_err_badName_obs}

Après un Scan, le nom du jeu de données (et donc son titre si la métadonnée est nouvelle) est le type de géométrie (point...) au lieu du nom du fichier/de la table.

#### Problème {#scan_err_badName_diagnostic}

Le Scan a été lancé avec une version de FME non compatible (FME 2018 ou 2017).

#### Solution {#scan_err_badName_solve}

Installer FME 2016.1 comme indiqué dans [les prérequis](prerequisites.html), puis redémarrer le service.
