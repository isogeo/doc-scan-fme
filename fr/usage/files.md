# Arborescence de fichiers <i class="fa fa-folder-open"></i>

![Point d&apos;entrée Fichiers](/assets/scanFME_new_files_btn.png "Sélecteur de type de point d&apos;entrée - Arborescence de fichiers")

Indiquer le chemin absolu d&apos;accès à une  arborescence de répertoires contenant les données géographiques.

## Caractéristiques et précisions

* les fichiers doivent être accessibles via un partage de type Windows (protocole [SMB](https://fr.wikipedia.org/wiki/Server_Message_Block)) ;

* il est préférable qu&apos;ils soient hébergés sur un serveur ;

* tous les sous-répertoires sont explorés et il est donc recommandé d&apos;indiquer une granularité assez fine (1 300 fichiers maximum par point d&apos;entrée) ;

* il n&apos;est pas possible de filtrer sur un format en particulier.

### Ajouter un répertoire de fichiers à scanner

Pour créer un point d’entrée « Fichiers » :

1. Dans le menu « Scan FME », créer un nouveau point d’entrée en cliquant sur « + Nouveau »
2. Sélectionnez le type « Fichier »
3. Nommez le point d’entrée. Exemple : « Cadastre »
4. Renseigner le chemin d’accès au répertoire contenant les données à scanner. Exemple : //serveur/partage/Dossier/

    ![Nouveau point d&apos;entrée fichiers](/assets/scanFME_new_files.png "Créer un nouveau point d&apos;entrée pour scanner des fichiers")

5. Sauvegarder. Le nouveau point d’entrée créé s’ajoute à la liste des points d’entrée. Il est prêt à être scanné.

    ![Nouveau point d&apos;entrée fichiers](/assets/scanFME_new_files_ready.png "Le nouveau point d&apos;entrée est prêt à être scanné")
