---
description: Créer un point d'entrée de type arborescence de fichiers pour le Scan FME Isogeo
---

# Système de fichiers <i class="fa fa-folder-open"></i> {#files}

Indiquer le chemin absolu d'accès à une arborescence de répertoires contenant les données géographiques.

## Caractéristiques et précisions {#precisions}

* les fichiers doivent être accessibles via un partage de type Windows (protocole [SMB](https://fr.wikipedia.org/wiki/Server_Message_Block)) ;

* il est préférable qu'ils soient hébergés sur un serveur ;

* tous les sous-répertoires sont explorés et il est donc recommandé d'indiquer une granularité assez fine (quelques centaines de fichiers maximum par point d'entrée) ;

* il est possible d'exclure des formats, des dossiers et des fichiers particuliers ;

* il est préférable d'indiquer le chemin physique (exemple : `//serveur/partage/dossier/`) plutôt que le lecteur réseau (exemple : `G:\alias\partage\dossier`).

### Ajouter un répertoire de fichiers à scanner {#add_repertory}

Pour créer un point d’entrée « Fichiers » :

1. Dans le menu « Scan FME », créer un nouveau point d’entrée en cliquant sur « + Créer » ;
2. Sélectionnez le type « Système de fichiers » ;
3. Renseigner les champs du point d'entrée répartis en quatre sections : 
  * Informations 
  * Métadonnées 
  * Inclusion de données 
  * Exclusion de donnée ;
4. Enregistrer et créer le point d'entrée.

#### Informations {#add_informations}

Informations générales du point d'entrée : Les champs de cette partie doivent obligatoirement être renseignés afin de pouvoir enregistrer et créer le point d'entrée.

1. Nommer le point d’entrée ;
2. Renseigner le chemin d’accès au répertoire contenant les données à scanner. Exemple : `//serveur/partage/dossier/`

    ![Renseigner le nom du point d'entrée et le chemin vers les données](/assets/New entrypoint - path.png)

#### Métadonnées {#add_metadata}

La section "Métadonnées", permet de sélectionner les étiquettes à associer à toutes les fiches du point d'entrée. Les champs de cette section sont optionnels.

**NOTE** : Les métadonnées sélectionnées dans le point d'entrée seront ajoutées à toutes les fiches de ce dernier, même si elles sont ajoutées après le premier scan.

Sélectionner les métadonnées de la liste suivante à associer aux fiches de métadonnées :

* Catalogues : Tous les catalogues du groupe de travail sur app.isogeo.com ;
* Thématiques : Seules les thématiques sélectionnées ;
* Thèmes INSPIRE : Tous les thèmes INSPIRE ;
* Mot-clés : La liste de mots-clés associés **OU** la liste restreinte de mots-clés.

L'ajout de nouvelles métadonnées se fait automatiquement lors d'un Scan.

#### Inclusion de données {#add_inclusions}

La section "Inclusion de données" permet la sélection des données du point d'entrée à scanner. Seules les données correspondant à au moins un des critères d'inclusion seront scannées. Les champs de cette partie sont optionnels.

Renseigner les trois champs en fonction du besoin :

* Formats de données : Sélectionner un ou plusieurs formats, de la liste prédéfinie, à inclure ;
* Dossiers : Ajouter le(s) chemin(s) absolu(s) du ou des sous-dossiers à inclure ;
* Données : Ajouter le(s) chemin(s) absolu(s) de la ou des données à inclure.

Il est possible, pour les trois types d'inclusion, d'importer une liste depuis un fichier CSV (cf. [Annexe sur le format du fichier CSV](/fr/appendices/csv.md)). Il est aussi possible de supprimer le contenu de chaque liste séparément.

#### Exclusion de données {#add_exclusions}

La section "Exclusion de données" permet la sélection des données du point d'entrée à ignorer par le Scan. Seules les données correspondant aucun critère d'exclusion seront scannées. Les champs de cette partie sont optionnels.

Renseigner les trois champs en fonction du besoin :

* Formats de données : Sélectionner un ou plusieurs formats, de la liste prédéfinie, à exclure ;
* Dossiers : Ajouter le(s) chemin(s) absolu(s) du ou des sous-dossiers à exclure ;
* Données : Ajouter le(s) chemin(s) absolu(s) de la ou des données à exclure.

Il est possible, pour les trois types d'exclusion, d'importer une liste depuis un fichier CSV (cf. [Annexe sur le format du fichier CSV](/fr/appendices/csv.md)). Il est aussi possible de supprimer le contenu de chaque liste séparément.

![Nouveau point d'entrée fichiers prêt à être scanné](/assets/new_files_ready.png)

### Concernant les ESRI FileGDB {#filegdb}

Quelques précisions concernant ce format :

* Pour scanner une FileGDB ESRI, il faut indiquer comme "Chemin du répertoire", le dossier dans lequel se situe la FGDB `.gdb`. Par exemple, pour scanner `C:\SIG\datas\FGDB\MyGDB.gdb` il faut indiquer `C:\SIG\datas\FGDB` comme "Chemin du répertoire" et non `C:\SIG\datas\FGDB\MyGDB.gdb`.
