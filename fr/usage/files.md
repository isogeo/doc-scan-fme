---
description: Créer un point d'entrée de type arborescence de fichiers pour le Scan FME Isogeo
---

# Arborescence de fichiers <i class="fa fa-folder-open"></i> {#files}

![Point dentrée Fichiers](/assets/new_files_btn.png "Sélecteur de type de point dentrée - Arborescence de fichiers")

Indiquer le chemin absolu daccès à une  arborescence de répertoires contenant les données géographiques.

## Caractéristiques et précisions {#precisions}

* les fichiers doivent être accessibles via un partage de type Windows (protocole [SMB](https://fr.wikipedia.org/wiki/Server_Message_Block)) ;

* il est préférable quils soient hébergés sur un serveur ;

* tous les sous-répertoires sont explorés et il est donc recommandé dindiquer une granularité assez fine (1 300 fichiers maximum par point dentrée) ;

* il nest pas possible de filtrer sur un format en particulier.

### Ajouter un répertoire de fichiers à scanner {#add_repertory}

Pour créer un point d’entrée « Fichiers » :

1. Dans le menu « Scan FME », créer un nouveau point d’entrée en cliquant sur « + Nouveau »
2. Sélectionnez le type « Fichier »
3. Nommez le point d’entrée. Exemple : « Cadastre »
4. Renseigner le chemin d’accès au répertoire contenant les données à scanner. Exemple : //serveur/partage/Dossier/

    ![Nouveau point dentrée fichiers](/assets/new_files.png "Créer un nouveau point dentrée pour scanner des fichiers")

5. Sauvegarder. Le nouveau point d’entrée créé s’ajoute à la liste des points d’entrée. Il est prêt à être scanné.

    ![Nouveau point dentrée fichiers](/assets/new_files_ready.png "Le nouveau point dentrée est prêt à être scanné")
