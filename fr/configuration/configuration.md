---
description: Utiliser une version spécifique de FME pour le service client du Scan FME (Isogeo)
---
# Configuration du service

Depuis la version 2.5, le service est entièrement configurable depuis l'interface. Pour modifier la configuration, ouvrez les détails du service en cliquant sur son nom en bleu dans la page d'accueil du scan, puis cliquer sur le bouton modifier.

![Configuration du service dans l'interface](/assets/config_service.png)

## Spécifier le chemin de la version de FME {#scan_specific_version}

Plusieurs versions de FME pouvant être installées sur une même machine, il est possible d'indiquer au service de Scan FME (Isogeo Worker) d'en utiliser une en particulier.

Le répertoire par défaut (variable *FME_HOME*) est détecté automatiquement et indiqué dans l'interface.
Pour utiliser une autre version de FME, il suffit d'indiquer le chemin vers son répertoire d'installation (celui contenant le fichier *fme.exe*) et d'enregistrer. 

![Configurer le chemin de FME](/assets/config_service_path_fme.png)

### Ancienne méthode (dépréciée) {#scan_specific_version_depreciated}

Pour les versions antérieures à la 2.5, le service est aussi configurable mais il faut effectuer les étapes suivantes : 

1. Arrêter le service Isogeo Worker via le gestionnaire de services de Windows ;
2. Dans le dossier `daemon` du dossier d'installation, ouvrir le fichier `worker.bat` dans un éditeur de texte (Notepad++, Sublime Text...)
3. En ligne **37**, indiquer entre guillemets le chemin vers le dossier d'installation de la version de FME souhaitée :

    ```batch
    :SetFmeHomePathHelper
    SET FME_HOME="C:\Program Files\FME\2016.1\"
    ```

    ![Scan FME - Chemin vers FME](/assets/install_fmePath_worker_set.png "Scan FME - Forcer la version de FME à utiliser")

4. Redémarrer le service `Isogeo Worker`.

Il est également possible de forcer la version par défaut de FME dans le système via la base de registre de Windows :

![Scan FME - Version par défaut système](/assets/install_fmePath_registry.png "Scan FME - Forcer la version de FME dans la base de registre")

## Version des scripts FME {#fme_scripts_version}

Selon la version détéctée automatiquement ou configurée ci-dessous, sélectionnez la version des scripts FME à utiliser.

* Pour les versions 2016 et inférieures, sélectionnez *2016*.
* Pour la version 2018, sélectionnez la version correspondante (version par défaut).

![Choisir la version des scripts FME](/assets/config_service_scripts_version.png)

## Paralléliser le Scan {#scan_concurrency}

Le service de scan permet d'utiliser jusqu'à 5 instances de FME à partir de la même licence. Par défaut, l'installation en utilise 3. L'utilisation de plusieurs instances FME améliore les performances du scan. Cependant, il faut que les capacités de votre serveur le permettent, le nombre de coeurs de votre processeur notamment (~ nb_coeurs - 1).

![Choisir le nombre d'instances de FME](/assets/config_service_max_concurrency.png)

### Ancienne méthode (dépréciée) {#scan_concurrency_depreciated}

**Si** le serveur est suffisamment dimensionné pour supporter cette charge, il suffit d'éditer le fichier *worker.bat* dans le dossier *daemon* de l'installation du scan et de modifier le paramètre `MAX_FME_CONCURRENCY_LIMIT` puis de redémarrer le service.

## Choix de la branche {#branch}

Les mises à jour étant automatiques, il est possible de choisir la branche que vous souhaitez utiliser. Il est recommandé de n'utiliser que la branche stable, sauf en cas de demande spécifique de la part de l'équipe Isogeo. Pour ce faire, il suffit de cocher la case ci-dessous et d'enregistrer.

![Choisir la branche de mise à jour du service](/assets/config_service_branch.png)