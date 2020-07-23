# Installer plusieurs services et les lier à un même FME {#scan_multiple_workers}

Pour les besoins des projets partenariaux où le Scan est mutualisé ou pour des besoins de cloisonnement des groupes de travail créant les fiches automatiquement, il est possible de lier plusieurs services du Scan à une seule installation de FME, sur un ou plusieurs serveurs.

Voici la marche à suivre pour 2 groupes de travail, lun nommé CA (le principal) et lautre CC ((le subsidiaire) :

## 1. Télécharger le service de Scan à partir de chaque groupe de travail :

| Dans le groupe principal |
| :----------------------: |
| ![Télécharger le service](/assets/install_muli_gt01.png "Télécharger le service depuis le groupe de travail n°1") |

| Dans le groupe subsidiaire |
| :------------------------: |
| ![Télécharger le service](/assets/install_muli_gt02.png "Télécharger le service depuis le groupe de travail n°2")   |

## 2. Organiser correctement les installations pour éviter les confusions. Arborescence type attendue :

![Arborescence type](/assets/install_muli_arborescence.png "Bien ranger les différents services")

## 3. Renommer les services dans les fichiers `install.bat` et `uninstall.bat` (sous-dossier *daemon*), en remplaçant les 3 occurrences de `Isogeo Worker` par un nom spécifique à chacun :

| Pour le groupe principal |
| :----------------------: |
| ![Editer les fichiers](/assets/install_muli_edited_files_gt01.png "Edition des fichiers dans un éditeur de texte") |

| Pour le groupe subsidiaire |
| :------------------------: |
| ![Editer les fichiers](/assets/install_muli_edited_files_gt02.png "Edition des fichiers dans un éditeur de texte") |

## 4. Lancer les fichiers `install.bat` et vérifier que les services sont bien enregistrés et fonctionnels :

![2 services installés sur le même serveur](/assets/install_multi_services.png "vérifier linstallation des 2 services")
