# Question et erreurs fréquentes

De  notre expérience dannées de support, dans la plupart des cas les soucis sont résolus en vérifiant de nouveau [les prérequis](prerequisites.html) puis en redémarrant le service. Sinon cette page peut peut-être répondre à votre problème, avant décrire au [support du Scan](support.html).

## Du côté de linstallation

Si le message suivant saffiche, veuillez vérifier [les prérequis](prerequisites.html), en particulier [les droits de lutilisateur configuré](prerequisites.html#compte-utilisateur) pour lancer le service.

![Service non démarré](/assets/install_errors_ServiceDoNotStart.png "Le service na pas démarré")

____

## Du côté de linterface

### Problème dauthentification \(Oups! Forbidden\) {#scan_err_ui_auth}

Après sêtre authentifié sur linterface du Scan FME, il arrive que le message ci-dessous saffiche. Il sagit dun problème qui peut intervenir lors de multiples authentifications à Isogeo dans différents onglets.

Pour résoudre le problème, cliquer sur https://daemons.isogeo.com/logout puis réessayez.

![Scan FME - Oups forbidden](/assets/error_forbidden.png "Scan FME - Problème dauthentification \(Oups! Forbidden\)")

### Impossible daccéder au chemin spécifié {#scan_err_ui_unreachable}

Si lun des messages ci-dessous saffiche, cest quil y a un problème avec les paramètres daccès aux données entrés dans le point dentrée : chemin, schém, base de données, droits utilisateur...

![Echec du scan](/assets/scan_errors_UnableToAccessEntryPoint.png "Impossible daccéder au chemin spécifié")

____

## Cas particuliers connus {#scan_known_cases}

### Shapefile supérieur à 2 Go {#scan_err_shp_too_big}

FME ne lit pas les shapefiles dont la taille de chaque composant (.shp / .dbf / .shx ...) dépasse les 2 Go, comme indiqué dans [la base de connaissance officielle](https://knowledge.safe.com/articles/772/fme-and-esri-arcgis-troubleshooting-guide.html) :

>  Note: Shape datasets larger than 2GB are considered invalid and will cause errors when opened in other applications.

Il sagit dailleurs dune limite inhérente au format, quEsri précise dans http://support.esri.com/technical-article/000010813[](http://support.esri.com/technical-article/000010813).

### Donnée géographique corrompue ou incohérente {#scan_err_corrupted_data}

Si un jeu de données contient un objet sans géomtrie, la donnée ne peut être lue jusquau bout par le Scan FME. Elle est donc indiquée dans la colonne erreur du détail de la requête du Scan avec la mantion "Impossible de lire la donnée".

Dans le fichier LOG, lerreur intervient sur létape "LookUp". Exemple tiré dune table PostGIS où le nombre denregistrement (lignes) était incohérent par rapport au nombre dobjets géométriques liés :

```json
{"worker":"wk-d864517e","level":"info","message":"(etl) Start new fme script from queue with options :  [ C:\\\\PROGRA~1\\\\Isogeo\\\\ISOGEO~1\\\\scripts\\\\lookup-postgis.fmw,\n  --OUTPUT_JSON,\n  C:\\\\PROGRA~1\\\\Isogeo\\\\ISOGEO~1\\\\tmp\\\\lookup-gC9aIjzL6,\n  --LOG_FILE,\n  C:\\\\PROGRA~1\\\\Isogeo\\\\ISOGEO~1\\\\tmp\\\\log-UUOBAvNXz,\n  --USERNAME,\n  isogeo,\n  --PASSWORD,\n  modepassepasse,\n  --SOURCE,\n  bdgeo_prod,\n  --HOST,\n  192.168.1.1,\n  --PORT,\n  5432,\n  --FEATURE_TYPES,\n  schema.dataset ]","timestamp":"2017-12-14T16:14:30.604Z"}
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
