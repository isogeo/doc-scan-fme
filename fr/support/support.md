# Support spécifique au Scan FME {#scan_suport}

En cas de problème et après avoir vérifié que l'erreur n'est pas documentée dans [la section dédiée](faq.html), voici la procédure pour envoyer un ticket au support.

## Eléments pour faciliter le diagnostic du support

Le service du Scan FME (nommé Isogeo Worker) étant le seul composant installé sur l'architecture informatique des clients, c'est celui qui exige le plus d'informations de la part du client. Afin d'assurer un support rapide, merci de lire attentivement les différents éléments à réviser ou joindre **avant de contacter le support**.

> NB : Ce diagnostic préalable doit également être réalisé si vous utilisez la version On-Premises d'Isogeo. Cependant, des étapes supplémentaires incluant votre administrateur système peuvent être necessaires (pour récupérer les logs du serveur du Scan notamment).

### Etapes classiques pour écarter les problèmes communs {#scan_auto_diag}

1. Vérifier les prérequis, notamment :

    * la communication vers les domaines Isogeo (voir [prérequis](/prerequisites.md)). Un changement de proxy ou pare-feu est si vite arrivé...
    * la licence FME et sa disponibilité durant tout la durée dun scan
    * les droits en lecture sur les données ciblées et les droits d'écriture sur le dossier d'installation du service

2. Ouvrir une session bureau à distance sur le serveur où est installé le service, **en s'identifiant avec l'utilisateur configuré pour lancer le service** puis :

    1. Redémarrer le service Isogeo Worker à partir de l'utilitaire des services Windows et relancer le Scan.
    ![Redémarrer le service Isogeo Worker](/assets/restart_isogeo_worker.png)
    2. Pour compléter le diagnostic, ouvrir FME Data Inspector dans la version utilisée par le Scan ;
    3. [ouvrir les jeux de données ciblés](https://desktopmanualbasic.safe.com/DesktopBasic1Basics/1.13.ViewingData.html) avec les mêmes paramètres d'accès (fichier de connexion, paramètres de bases de donnée, chemin du répertoire...) que ceux entrés dans les points d'entrée du Scan FME.

3. S'assurer que le point d'entrée configuré n'accède pas à plus de 1 300 jeux de données. Créer des points d'accès plus fins.

### Récupérer les logs du service de Scan {#scan_log_srv}

Le service Isogeo Worker produit plusieurs types de logs (fichiers de journalisation des opérations et erreurs d'un processus informatique - [fiche Wikipédia [en]](https://en.wikipedia.org/wiki/Log_file)). Celui à joindre est celui contenu dans le dossier `dossier_installation_isogeo\logs` :

![Fichier de log](/assets/install_log_file.png)

<!-- ### Liens directs {#direct_link}

Afin d'accéder rapidement à la bonne requête du Scan, joindre l'URL directe ou du moins celle du point d'entrée :

![URL unique des requêtes](/assets/request_url.png "Récupérer l'URL directe d'une requête du Scan")

Exemples :

* <https://app.isogeo.com/groups/08b3054757544463abd06f3ab51ee491/admin/isogeo-worker/entrypoints/56f9232db5b9172c054c1860/requests/59d7912936046e0050d61a7f>
* <https://scan.isogeo.com/g/08b3054757544463abd06f3ab51ee491/entrypoints/56f9232db5b9172c054c1860/requests/59d7912936046e0050d61a7f> -->

### Récupérer les logs des workbenches FME 

Les logs des workbenches FME sont générés dans le dossier `dossier_installation_isogeo\tmp` mais ne sont pas conservés par défaut. Pour que leur suppression ne soit pas réalisée, il est possible de changer la configuration du service en éditant le fichier `dossier_installation_isogeo\env.json` et remplacer la ligne `"keepTmp" : false` par `"keepTmp" : true`.

![Exemple de env.json](/assets/support_keepTmp.png)

Une fois le service redémarré et le scan relancé, les logs FME ne se supprimeront plus. 

Attention, laisser ce mode activé génère une large quantité de fichiers. Il est donc recommendé de l'activer seulement dans une optique de débugage et de le désactiver une fois le débugage terminé. Une fois le client redémarré, il supprimera de lui-même les fichiers de logs qui avaient été conservés. 

### Récupérer les informations sur le contexte FME (FMEReport.html) {#scan_log_fme}

Safe Software, l'éditeur de FME, met un petit outil à disposition pour générer un rapport de diagnostic complet et lisible sur l'environnement logiciel autour de l'ETL (système d'exploitation, version de FME installée, présence de logiciels tiers comme Esri, Oracle...). 
Il est présenté dans [cet article de la base de connaissance partagée de FME](https://knowledge.safe.com/articles/714/general-troubleshooting-gathering-system-informati.html) et [détaillé dans celui-ci](https://knowledge.safe.com/articles/692/a-guide-to-interpreting-the-system-information-bat.html).

Pour l'utiliser, les **droits d'administrateur** sur la machine où FME est installé sont requis :

1. Lancer le fichier `system_information.bat` dans le dossier *deamon* du répertoire d'installation du service.
2. Clic droit > "Exécuter en tant qu'administrateur" ;

Joindre à votre mail le fichier `FMEReport.html`, généré à côté du fichier `system_information.bat` ainsi que sur le bureau.

## Envoyer le mail {#mail}

Cliquer ici pour envoyer un mail enrichi des éléments ci-dessus à [support@isogeo.fr](mailto:support+scan@isogeo.fr?subject=TITRE_PROBLEME_ICI&cc=projets@isogeo.fr)
