# Support spécifique au Scan FME {#scan_suport}

En cas de problème et après avoir vérifié que lerreur nest pas documentée dans [la section dédiée](faq.html), voici la procédure pour envoyer un ticket au support.

## Eléments pour faciliter le diagnostic du support

Le service du Scan FME (nommé Isogeo Worker) étant le seul composant installé sur larchitecture informatique des clients, cest celui qui exige le plus dinformations de la part du client. Afin dassurer un support rapide, merci de lire attentivement les différetnts éléments à réviser ou joindre **avant de contacter le support**.

### Etapes classiques pour écarter les problèmes communs {#scan_auto_diag}

1. Vérifier les prérequis, notamment :

    * louverture du port TCP 5671 vers les domaines Isogeo (voir prérequis). Un changement de proxy ou pare-feu est si vite arrivé...
    * la licence FME et sa disponibilité durant tout la durée dun scan
    * les droits en lecture sur les données ciblées et les droits décriture sur le dossier dinstallation du service

2. Ouvrir une session bureau à distance sur le serveur où est installé le service, **en sidentifiant avec lutilisateur configuré pour lancer le service** puis :

    1. ouvrir FME Data Inspector
    2. [ouvrir les jeux de données ciblés](https://desktopmanualbasic.safe.com/DesktopBasic1Basics/1.13.ViewingData.html) avec les mêmes paramètres daccès (fichier de connexion, chemin...) que ceux entrés dans les points dentrée du Scan FME

3. Sassurer que le point dentrée configuré naccède pas à plus de 1 300 jeux de données. Créer des points daccès plus fins.

### Récupérer les logs du service de Scan {#scan_log_srv}

Le service Isogeo Worker produit plusieurs types de log (fichiers de journalisation des opérations et erreurs dun processus informatique - [fiche Wikipédia [en]](https://en.wikipedia.org/wiki/Log_file)). Celui à joindre est celui contenu dans le dossier `dossier_installation_isogeo\daemon\logs` :

![Scan FME - Fichier de log](/assets/install_log_file.png "Fichier log du service Isogeo Worker (Scan FME)")

### Liens directs

Afin daccéder rapidement à la bonne requête du Scan, joindre lURL directe ou du moins celle du point dentrée :

![Scan FME - URL unique des requêtes](/assets/request_url.png "Récupérer lURL directe dune requête du Scan")

Exemples :

* <https://app.isogeo.com/groups/08b3054757544463abd06f3ab51ee491/admin/isogeo-worker/entrypoints/56f9232db5b9172c054c1860/requests/59d7912936046e0050d61a7f>
* <https://daemons.isogeo.com/g/08b3054757544463abd06f3ab51ee491/entrypoints/56f9232db5b9172c054c1860/requests/59d7912936046e0050d61a7f>

### Récupérer les informations sur le contexte FME (FMEReport.html) {#scan_log_fme}

Safe Software, léditeur de FME, met un petit outil à disposition pour générer un rapport de diagnostic complet et lisible sur lenvironnement logiciel autour de lETL (système dexploitation, version de FME installée, présence de logiciels tiers comme Esri, Oracle...). Il est présenté dans [cet article de la base de connaissance partagée de FME](https://knowledge.safe.com/articles/714/general-troubleshooting-gathering-system-informati.html) et [détaillé dans celui-ci](https://knowledge.safe.com/articles/692/a-guide-to-interpreting-the-system-information-bat.html).

Pour lutiliser, les **droits dadministrateur** sur la machine où FME est installé sont requis :

1. [Télécharger le fichier `system_information.bat`](https://cdn.rawgit.com/safesoftware/system-information-batch/master/system_information.bat) ;
2. Clic droit > "Exécuter en tant quadministrateur" ;

Joindre à votre mail le fichier `FMEReport.html`, généré à côté du fichier `system_information.bat` ainsi que sur le bureau.

## Envoyer le mail

Cliquer ici pour envoyer un mail enrichi des éléments ci-dessus à [support@isogeo.fr](mailto:support+scan@isogeo.fr?subject=Scan FME - TITRE_PROBLEME_ICI&cc=projets@isogeo.fr)
