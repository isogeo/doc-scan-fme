# Utiliser une version spécifique de FME {#scan_specific_version}

Plusieurs versions de FME pouvant être installées sur une même machine, il est possible dindiquer au service de Scan FME (Isogeo Worker) den utiliser une en particulier :

1. Arrêter le service Isogeo Worker via le gestionnaire de services de Windows ;
2. Dans le dossier `daemon` du dossier dinstallation, ouvrir le fichier `worker.bat` dans un éditeur de texte (Notepad++, Sublime Text...)
3. En ligne **37**, indiquer entre guillemets le chemin vers le dossier dinstallation de la version de FME souhaitée :

    ```batch
    :SetFmeHomePathHelper
    SET FME_HOME="C:\Program Files\FME\2016.1\"
    ```

    ![Scan FME - Chemin vers FME](/assets/install_fmePath_worker_set.png "Scan FME - Forcer la version de FME à utiliser")

4. Redémarrer le service `Isogeo Worker`.

Il est également possible de forcer la version par défaut de FME dans le système via la base de registre de Windows :

![Scan FME - Version par défaut système](/assets/install_fmePath_registry.png "Scan FME - Forcer la version de FME dans la base de registre")
