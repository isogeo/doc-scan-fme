# Configuration et usages avancés

## Utiliser une version spécifique de FME {#scan_specific_version}

Plusieurs versions de FME pouvant être installées sur une même machine, il est possible d&apos;indiquer au service de Scan FME (Isogeo Worker) d&apos;en utiliser une en particulier :

1. Arrêter le service Isogeo Worker via le gestionnaire de services de Windows ;
2. Dans le dossier `daemon` du dossier d&apos;installation, ouvrir le fichier `worker.bat` dans un éditeur de texte (Notepad++, Sublime Text...)
3. En ligne **37**, indiquer entre guillemets le chemin vers le dossier d&apos;installation de la version de FME souhaitée :

	```dos
	:SetFmeHomePathHelper
	SET FME_HOME="C:\Program Files\FME\2016.1\"
	```

	![Scan FME - Chemin vers FME](/assets/scanFME/scanFME_install_fmePath_worker_set.png "Scan FME - Forcer la version de FME à utiliser")


4. Redémarrer le service `Isogeo Worker`.

Il est également possible de forcer la version par défaut de FME dans le système via la base de registre de Windows :

![Scan FME - Version par défaut système](/assets/scanFME/scanFME_install_fmePath_registry.png "Scan FME - Forcer la version de FME dans la base de registre")

---

## Installer plusieurs services et les lier à un même FME {#scan_multiple_workers}

Pour les besoins des projets partenariaux où le Scan est mutualisé ou pour des besoins de cloisonnement des groupes de travail créant les fiches automatiquement, il est possible de lier plusieurs services du Scan à une seule installation de FME, sur un ou plusieurs serveurs.

Voici la marche à suivre pour 2 groupes de travail, l&apos;un nommé CA (le principal) et l&apos;autre CC ((le subsidiaire) :

1- Télécharger le service de Scan à partir de chaque groupe de travail :

| Dans le groupe principal | Dans le groupe subsidiaire |
| :----------------------: | :----------------------: |
| ![Télécharger le service](/assets/scanFME/scanFME_install_muli_gt01.png "Télécharger le service depuis le groupe de travail n°1") | ![Télécharger le service](/assets/scanFME/scanFME_install_muli_gt02.png "Télécharger le service depuis le groupe de travail n°2") |

2- Organiser correctement les installations pour éviter les confusions. Arborescence type attendue :

![Arborescence type](/assets/scanFME/scanFME_install_muli_arborescence.png "Bien ranger les différents services")

3- Renommer les services dans les fichiers `install.bat` et `uninstall.bat` (sous-dossier *daemon*), en remplaçant les 3 occurrences de `Isogeo Worker` par un nom spécifique à chacun :

| Pour le groupe principal | Pour le groupe subsidiaire |
| :----------------------: | :------------------------: |
| ![Editer les fichiers](/assets/scanFME/scanFME_install_muli_edited_files_gt01.png "Edition des fichiers dans un éditeur de texte") | ![Editer les fichiers](/assets/scanFME/scanFME_install_muli_edited_files_gt02.png "Edition des fichiers dans un éditeur de texte") |

4- Lancer les fichiers `install.bat` et vérifier que les services sont bien enregistrés et fonctionnels :

![2 services installés sur le même serveur](/assets/scanFME/scanFME_install_muli_services.png "vérifier l&apos;installation des 2 services")

---

## Accélérer le Scan {#scan_concurrency}

Le service de scan permet d&apos;utiliser jusqu&apos;à 5 instances de FME à partir de la même licence. Par défaut, l&apos;installation en utilise 3.

**Si** le serveur est suffisamment dimensionné pour supporter cette charge, il suffit d&apos;éditer le fichier *worker.bat* dans le dossier *daemon* de l&apos;installation du scan et de modifier le paramètre `MAX_FME_CONCURRENCY_LIMIT` puis de redémarrer le service.
