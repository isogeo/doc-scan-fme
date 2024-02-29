---
description: Consulter la liste des ressources scannées et des informations 
---

# Page Ressources

La page `Ressources` constitue l'inventaire de l'ensemble des ressources scannées. 

Cette page est composée de deux onglets : 

* un onglet `Ressources` listant toutes les ressources scannées dans un tableau selon des critères de filtre ;
* un onglet `Paramètres avancés` permettant de fixer les paramètres d’affichage de la liste de ressources. 

## Onglet Ressources {#ressources}

Au chargement de la page, le tableau présente l'ensemble des ressources (données et services) dont le scan a abouti au moins une fois. On ne retrouve donc pas les données en erreur ou celles retirées de la liste. En effet, si une donnée n'est plus présente dans votre patrimoine, vous pouvez la retirer de la liste une fois sa fiche de métadonnée supprimée du catalogue (cf. [Identifier les ressources qui ne sont plus détectées dans le patrimoine pour les supprimer du catalogue](#identify_data_to_delete)). 

![Retirer de la liste les données](/assets/exclusion_red_data_from_inventory.png)

Vous pouvez  filtrer les resources selon les critères suivants (en **gras** les critères avec plusieurs valeurs possibles) : 

* Recherche textuelle : filtrez sur toutes les resources dans laquelle on retrouve la chaîne de caractère recherchée dans le nom. Par exemple en tapant "plu" ; ![Rechercher une chaine de caractère](/assets/ressources_search_data.png)
* **Format de la ressource** (ex : esrigdb, jp2, EMS etc.) ;
* **Dernier statut remonté par le scan** (inchangé, modifié, structure modifiée, déplacé, nouveau, ignoré) ;
![Filtrer sur un ou plusieurs statut](/assets/ressources_status_filter.png)
* **Point d'entrée** : Choisissez le ou les point(s) d'entrée correspondant(s) ;
* Date du *dernier Scan* ou *de la dernière mise à jour de la métadonnée* : Sélectionner la période correspondante à la date recherchée.  

Vous pouvez également exporter la recherche en csv à l'aide du bouton correspondant. Celui contient l'ensemble des informations affichables dans le tableau. 

## Onglet Paramètres avancés {#advanced_parameters}

### Conditions d'affichage des ressources {#conditions}

L'onglet Ressources présente toutes les données dont les conditions respectent les paramètres avancés. 
Vous pouvez donc isoler des ressources selon les conditions d'affichage suivantes :

* Présence de la ressource dans le catalogue
  * présente dans le catalogue
  * non présente dans le catalogue
* Présence de la ressource dans les derniers scans de ses points d'entrée
  * remontée dans le dernier scan d'au moins un de ses points d'entrée
  * non remontée dans le dernier scan de tous ses points d'entrée
* Inclusion/exclusion de la ressource dans ses points d'entrée
  * incluse dans au moins un point d'entrée qui l'a déjà scannée
  * exclue dans tous les points d'entrée qui l'ont déjà scannée
* Origine de la ressource
  * issue d'un point d'entrée supprimé
  * issue d'un seul point d'entrée
  * issue de plusieurs points d'entrée

> Règle d'affichage : Les ressources respectant les 4 conditions sont affichées. Pour chacune des conditions, les ressources respectant l'une ou l'autre sont affichées. 

### Affichage des informations sur les ressources {#columns}

L'onglet Paramètres avancés permet de choisir les colonnes à afficher dans le tableau. Ce choix est conservé à chaque réouverture de la page Ressources. 

* Format : format de la donnée 
* Date de la dernière mise jour :  date de la dernière mise à jour de la métadonnée par le Scan (= date de la dernière détection de la ressource comme *nouvelle* ou *modifiée*)
* Date du dernier scan : date du dernier scan de la ressource
* Lien vers la dernière requête : lien vers la dernière requête qui a scanné la ressource
* Dernier statut : dernier statut (inchangé, modifié, structure modifiée, déplacé, nouveau, ignoré) remonté par le dernier scan de la ressource
* Différence d'entités : différence du nombre d'entités détectées sur des données détectées comme modifiées lors du dernier scan
* Différence d'entités (%) : pourcentage de cette différence par rapport au nombre total d'entités détectées lors du scan précédent
* Différence d'attributs : différence du nombre d'attributs détectés sur des données dont la structure a été détectée comme modifiée lors du dernier scan
* Attributs ajoutés et supprimés : colonnes permettant d'afficher le nombre d'attributs ajoutés et le nombre d'attributs supprimés sur des données dont la structure a été modifiée
* Lien vers la fiche : lien vers la fiche dans l'interface d'administration du catalogue
* Actions : bouton permettant de retirer des ressources de la liste ou de gérer les exclusions de leurs points d'entrée

## Cas d'usages {#usages}

Nous avons identifié plusieurs cas d'usage de la page Ressources qui vous aideront pour l'administration, la gestion et le suivi de votre patrimoine de donnée et de son catalogue associé. 

### Afficher les informations sur les modifications des données {#information} 

La page ressources permet d’avoir un affichage tabulaire concis des modifications de l’intégralité des données scannées. Il est notamment possible d’avoir la liste des données modifiées lors du dernier scan en filtrant selon les statuts de la donnée au dernier scan (Modifié et Structure Modifiée).

Pour plus d’informations sur les modifications, il est possible d’activer les colonnes suivantes dans l’onglet “Paramètres avancés” : 
* Différence d'entités : La colonne affiche la différence d’entités entre les deux derniers scans.
* Différence d'entités (%) : La colonne permet d’avoir une idée de l’ampleur des modifications d’entités entre le précédent et le dernier scan.
* Attributs ajoutés et supprimés : Une colonne affiche le nombre d’attributs ajoutés, une autre affiche le nombre d’attributs supprimés. En dépliant la donnée, il est possible de voir le détail des attributs ajoutés et supprimés.
* Différence d’attributs : La colonne affiche la différence d’attributs entre la donnée au dernier scan et la donnée au scan précédent. 

Pour chacune de ses colonnes, il est possible de trier les valeurs selon l’ordre croissant ou décroissant afin d’identifier rapidement les données ayant subi le plus de modifications. 

#### Identifier les données ayant subit le plus de modification de leur nombre d'entités {#entities}

Par exemple, en triant par *Entités (%) décroissant*, vous pouvez identifier rapidement les données qui ont été purgées. En inversant le tri, vous pouvez détecter les données qui ont été fortement remplies. 

#### Identifier les données ayant de nouveaux attributs à documenter {#attributes}

En filtrant sur le statut *Structure modifiée*, seules les données ayant eu des attributs ajoutés ou supprimées sont affichées. En cliquant sur le détail de la donnée, la liste des attributs ajoutés et supprimés s'affiche. Vous pouvez ensuite cliquer sur le lien vers la fiche pour aller documenter les nouveaux attributs détectés. 

![Identifier les données avec de nouveaux attributs](/assets/ressources_structure_modified.png)

### Identifier les ressources qui ne sont plus détectées dans le patrimoine pour les supprimer du catalogue {#identify_data_to_delete}

Une ressource n’existe plus dans votre patrimoine et vous souhaitez facilement supprimer sa fiche de métadonnées du catalogue ? 

Par défaut, ces ressources sont signalées en **rouge** dans le tableau. Vous pouvez donc ouvrir la fiche de métadonnée puis la supprimer du catalogue. Elle apparaîtra alors comme supprimée dans le tableau de la page Ressources. Vous pouvez ensuite la retirer de la liste (*bouton Action : retirer de la liste*) si vous ne souhaitez plus la voir afficher dans le tableau.

Un filtre des paramètres avancés permet cependant de les récupérer encore plus facilement. Pour cela, simplement : 

1. Ouvrir l'onglet *Paramètres avancés* ;
2. désactiver la condition d'affichage *"remontée dans le dernier scan d'au moins un de ses points d'entrée”*, en laissant seulement activée la condition *“non remontée dans le dernier scan de tous ses points d'entrée”* ;
3. revenir à l'onglet *Ressources* : désormais, toutes les ressources affichées dans le tableau sont des ressources qui ne sont plus scannées.

![Afficher les ressources qui ne sont plus scannées](/assets/ressources_not_in_last_scans.png)

### Identifier les ressources qui n’ont pas été scannées depuis longtemps et qui pourraient bénéficier d’un nouveau scan {#any_scan_since_a_long_time}

La page Ressources aide également au suivi de la fréquence des scans. Elle facilite la récupération de la date du dernier scan des différentes ressources. Ainsi, il est facile de trouver les ressources qui n’ont pas été scannées depuis un certain temps. 

Pour cela :

1. Sélectionner tous les statuts possibles ;
2. choisir la *date du dernier scan* ;
3. sélectionner une période de temps pour la date du dernier scan. 

![Afficher les ressources qui ne sont plus scannées depuis un certain temps](/assets/ressources_not_scan_since_a_long_time.png)

Ces ressources mériteraient d’être scannées à nouveau pour assurer l’actualité de la fiche de métadonnées. Pour les données, il suffit de cliquer sur le lien de la dernière requête dans le tableau ou le lien vers le point d’entrée dans le détail de la donnée puis de cliquer sur le bouton Scanner. 

Pour les services, contacter votre chef de projet dédié pour réaliser un recensement supplémentaire dans le cadre de la prestation de Scan des services ArcGIS Server.

### Identifier les données scannées sans fiche correspondante dans le catalogue {#ressources_with_no_metadata}

Pour détecter les données scannées n’ayant pas ou plus de fiche dans l’inventaire. Dans l’onglet “paramètres avancés” : 

1. Ouvrir l'onglet *Paramètres avancés* ;
2. ajouter la colonne *“Lien vers la fiche"* ;
3. désactiver la condition d'affichage *"présente dans le catalogue”*, en laissant seulement activée la condition *“non présente dans le catalogue”* ;
4. revenir à l'onglet *Ressources* : seules les ressources sans fiches correspondantes dans le catalogue seront affichées.

Cela peut concerner les ressources : 

* dont la fiche a été supprimée manuellement. Si ce n’est pas déjà le cas et que la donnée n’a pas d’utilité dans le catalogage, il faut donc l’exclure du Scan (*"Bouton Actions” > “Exclure/Gérer les exclusions”* depuis la page Ressources) pour que sa fiche ne soit pas récrée lors du prochain scan.
  * Ces ressources ont le lien vers leur fiche indiquée comme “Supprimée”. 
  * Pour voir seulement les données non exclues, il est possible de combiner avec la condition *“exclue dans tous les points d'entrée qui l'ont déjà scannée”* dans les paramètres avancés. 
* dont la création n’a pas fonctionné correctement. Il faut alors rescanner le point d’entrée et contacter le support Isogeo si le problème persiste en indiquant le nom de la donnée correspondante. 
  * Rien n’est indiqué dans la colonne *“Fiche"*

### Retrouver facilement le ou les point(s) d’entrée qui scanne(nt) une donnée pour la scanner ou l'exclure {#find_entrypoints}

Pour scanner une donnée, il faut savoir depuis quel(s) point(s) d’entrée elle est scannée. En fonction du nombre de points d’entrée, ce n’est pas forcément évident. Il est donc possible de récupérer l’information depuis la liste des ressources : 

1. Rechercher la donnée avec les filtres disponibles (recherche textuelle, en utilisant le format, …)
2. Cliquer sur la donnée recherchée
3. Récupérer la liste des points d’entrée. Depuis le point d’entrée choisi, relancer le Scan. Pour information, il est possible d’utiliser un critère d’inclusion pour scanner uniquement la donnée correspondante.
4. Vous pouvez également exclure la donnée des points d’entrée qui ne “devraient” pas la scanner (*“Bouton Actions” > “Exclure/Gérer les exclusions”*)
![Trouver les points d'entrée et gérer les exclusions](/assets/ressources_find_entrypoint.png)
5. Une popup s’ouvre alors pour choisir le point d’entrée où appliquer l’exclusion. Seuls les points d’entrée où aucun autre critère d’exclusion (format, dossier, schema) excluent déjà la donnée sont proposés.
6. Sélectionner le point d'entrée correspondant et cliquer sur Exclure.
![Exclure d'un point d'entrée](/assets/ressources_exclusion_from_entrypoint.png)

### Exporter les résultats d’une requête du scan {#export}

Pour exporter au format csv le résultat de la dernière requête d’un point d’entrée : 

1. Sélectionner le point d’entrée de cette requête dans les filtres 
2. Cliquer sur le bouton *Exporter la recherche*
![Export d'une requête](/assets/ressources_search_export.png)
3. Un fichier CSV est généré contenant toutes les colonnes peu importe celles qui sont activées dans les *Paramètres avancés*.
![Tableau exporté](/assets/ressources_export_table.png)
