---
description: Créer un point d'entrée de type arborescence de fichiers pour le Scan FME Isogeo
---

# Système de fichiers <i class="fa fa-folder-open"></i> {#files}

Indiquer le chemin absolu d'accès à une arborescence de répertoires contenant les données géographiques.

## Caractéristiques et précisions {#precisions}

* les fichiers doivent être accessibles via un partage de type Windows (protocole [SMB](https://fr.wikipedia.org/wiki/Server_Message_Block)) ;

* il est préférable qu'ils soient hébergés sur un serveur ;

* tous les sous-répertoires sont explorés et il est donc recommandé d'indiquer une granularité assez fine (quelques centaines de fichiers maximum par point d'entrée) ;

* il est possible d'exclure des formats, des dossiers et des fichiers particuliers.

* il est préférable d'indiquer le chemin physique (exemple : //serveur/partage/dossier/) plutôt que le lecteur réseau (exemple : G:\alias\partage\dossier)

### Ajouter un répertoire de fichiers à scanner {#add_repertory}

Pour créer un point d’entrée « Fichiers » :

1. Dans le menu « Scan FME », créer un nouveau point d’entrée en cliquant sur « + Nouveau... »
2. Sélectionnez le type « Système de fichiers »
3. Nommez le point d’entrée.
4. Renseigner le chemin d’accès au répertoire contenant les données à scanner. Exemple : //serveur/partage/dossier/

    ![Nouveau point d'entrée fichiers](/assets/new_files.png)

5. Choisir dans quel(s) catalogue(s) vous souhaitez ajouter automatiquement les nouvelles données scannées en le(s) sélectionnant (en général 1 catalogue de suivi et 1 catalogue thématique) 
6. Si besoin, choisir de remonter ou non les données non géographiques et/ou d'exclure un format de donnée et/ou des dossiers/fichiers.
7. Sauvegarder. Le nouveau point d’entrée créé s’ajoute à la liste des points d’entrée. Il est prêt à être scanné.

    ![Nouveau point d'entrée fichiers prêt à être scanné](/assets/new_files_ready.png)

### Concernant les ESRI FileGDB {#filegdb}

Quelques précisions concernant ce format :

* Pour scanner une FileGDB ESRI, il faut indiquer comme "Chemin du répertoire", le dossier dans lequel se situe la FGDB `.gdb`. Par exemple, pour scanner `C:\SIG\datas\FGDB\MyGDB.gdb` il faut indiquer `C:\SIG\datas\FGDB` comme "Chemin du répertoire" et non `C:\SIG\datas\FGDB\MyGDB.gdb`.
* Dans le cas où le répertoire indiqué contient plusieurs FGDB `.gdb`, si le nombre de FGDB `.gdb` est supérieur au [nombre d'appels FME simultanés](/configuration/configuration.html#scan_concurrency) configuré pour le service, il est probable que toutes les données ne soient pas recensées et que le résultat du scan varie d'une requête à l'autre. Par conséquent, nous vous recommandons de faire attention au nombre de FGDB `.gdb` présents dans un même dossier.
