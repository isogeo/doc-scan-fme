---
description: Consulter quelques cas d'usage de la page Ressources du Scan Isogeo. 
---

# Cas d'usages {#usages}

Nous avons identifié plusieurs cas d'usage de la page Ressources qui vous aideront pour l'administration, la gestion et le suivi de votre patrimoine de donnée et de son catalogue associé. 

## Afficher les informations sur les modifications des données {#information} 

La page ressources permet d’avoir un affichage tabulaire concis des modifications de l’intégralité des données scannées. Il est notamment possible d’avoir la liste des données modifiées lors du dernier scan en filtrant selon les statuts de la donnée au dernier scan (Modifié et Structure Modifiée).

Pour plus d’informations sur les modifications, il est possible d’activer les colonnes suivantes dans l’onglet “Paramètres avancés” : 
* Différence d'entités : La colonne affiche la différence d’entités entre les deux derniers scans.
* Différence d'entités (%) : La colonne permet d’avoir une idée de l’ampleur des modifications d’entités entre le précédent et le dernier scan.
* Attributs ajoutés et supprimés : Une colonne affiche le nombre d’attributs ajoutés, une autre affiche le nombre d’attributs supprimés. En dépliant la donnée, il est possible de voir le détail des attributs ajoutés et supprimés.
* Différence d’attributs : La colonne affiche la différence d’attributs entre la donnée au dernier scan et la donnée au scan précédent. 

Pour chacune de ses colonnes, il est possible de trier les valeurs selon l’ordre croissant ou décroissant afin d’identifier rapidement les données ayant subi le plus de modifications. 

### Identifier les données ayant subit le plus de modification de leur nombre d'entités {#entities}

Par exemple, en triant par *Entités (%) décroissant*, vous pouvez identifier rapidement les données qui ont été purgées. En inversant le tri, vous pouvez détecter les données qui ont été fortement remplies. 

![Identifier les données purgées](/assets/ressources_purge_data.png)

### Identifier les données ayant de nouveaux attributs à documenter {#attributes}

En filtrant sur le statut *Structure modifiée*, seules les données ayant eu des attributs ajoutés ou supprimées sont affichées. En cliquant sur le détail de la donnée, la liste des attributs ajoutés et supprimés s'affiche. Vous pouvez trier la colonne *Attribut* pour afficher les données ayant eu le plus de modification d'attribut. Vous pouvez ensuite cliquer sur le lien vers la fiche pour aller documenter les nouveaux attributs détectés. 

![Identifier les données avec de nouveaux attributs](/assets/ressources_structure_modified.png)

## Identifier les ressources qui ne sont plus détectées dans le patrimoine pour les supprimer du catalogue {#identify_data_to_delete}

Une ressource n’existe plus dans votre patrimoine et vous souhaitez facilement supprimer sa fiche de métadonnées du catalogue ? 

Par défaut, ces ressources sont signalées en **rouge** dans le tableau. Vous pouvez donc ouvrir la fiche de métadonnée puis la supprimer du catalogue. Elle apparaîtra alors comme supprimée dans le tableau de la page Ressources. Vous pouvez ensuite la retirer de la liste (*bouton Action : retirer de la liste*) si vous ne souhaitez plus la voir afficher dans le tableau.

Un filtre des paramètres avancés permet cependant de les récupérer encore plus facilement. Pour cela, simplement : 

1. Ouvrir l'onglet *Paramètres avancés* ;
2. désactiver la condition d'affichage *"remontée dans le dernier scan d'au moins un de ses points d'entrée”*, en laissant seulement activée la condition *“non remontée dans le dernier scan de tous ses points d'entrée”* ;
3. revenir à l'onglet *Ressources* : désormais, toutes les ressources affichées dans le tableau sont des ressources qui ne sont plus scannées.

![Afficher les ressources qui ne sont plus scannées](/assets/ressources_not_in_last_scans.png)

## Identifier les ressources qui n’ont pas été scannées depuis longtemps et qui pourraient bénéficier d’un nouveau scan {#any_scan_since_a_long_time}

La page Ressources aide également au suivi de la fréquence des scans. Elle facilite la récupération de la date du dernier scan des différentes ressources. Ainsi, il est facile de trouver les ressources qui n’ont pas été scannées depuis un certain temps. 

Pour cela :

1. Sélectionner tous les statuts possibles ;
2. choisir la *date du dernier scan* ;
3. sélectionner une période de temps pour la date du dernier scan. 

![Afficher les ressources qui ne sont plus scannées depuis un certain temps](/assets/ressources_not_scan_since_a_long_time.png)

Ces ressources mériteraient d’être scannées à nouveau pour assurer l’actualité de la fiche de métadonnées. Pour les données, il suffit de cliquer sur le lien de la dernière requête dans le tableau ou le lien vers le point d’entrée dans le détail de la donnée puis de cliquer sur le bouton Scanner. 

Pour les services, contacter votre chef de projet dédié pour réaliser un recensement supplémentaire dans le cadre de la prestation de Scan des services ArcGIS Server.

## Identifier les ressources scannées sans fiche correspondante dans le catalogue {#ressources_with_no_metadata}

Pour détecter les ressources scannées n’ayant pas ou plus de fiche dans l’inventaire. Dans l’onglet *Paramètres avancés* : 

1. Ouvrir l'onglet *Paramètres avancés* ;
2. ajouter la colonne *“Lien vers la fiche"* ;
3. désactiver la condition d'affichage *"présente dans le catalogue”*, en laissant seulement activée la condition *“non présente dans le catalogue”* ;
4. revenir à l'onglet *Ressources* : seules les ressources sans fiches correspondantes dans le catalogue seront affichées.

![Afficher les ressources sans fiche dans le catalogue](/assets/ressources_identify_data_without_metadata.png)

Cela peut concerner les ressources : 

* dont la fiche a été supprimée manuellement. Si ce n’est pas déjà le cas et que la donnée n’a pas d’utilité dans le catalogage, il faut donc l’exclure du Scan (*"Bouton Actions” > “Exclure/Gérer les exclusions”* depuis la page Ressources) pour que sa fiche ne soit pas récrée lors du prochain scan.
  * Ces ressources ont le lien vers leur fiche indiquée comme “Supprimée”. 
  * Pour voir seulement les données non exclues, il est possible de combiner avec la condition *“exclue dans tous les points d'entrée qui l'ont déjà scannée”* dans les paramètres avancés. 
* dont la création n’a pas fonctionné correctement. Il faut alors rescanner le point d’entrée et contacter le support Isogeo si le problème persiste en indiquant le nom de la donnée correspondante. 
  * Rien n’est indiqué dans la colonne *“Fiche"*

## Retrouver facilement le ou les point(s) d’entrée qui scanne(nt) une donnée pour la scanner ou l'exclure {#find_entrypoints}

Pour scanner une donnée, il faut savoir depuis quel(s) point(s) d’entrée elle est scannée. En fonction du nombre de points d’entrée, ce n’est pas forcément évident. Il est donc possible de récupérer l’information depuis la liste des ressources : 

1. Rechercher la donnée avec les filtres disponibles (recherche textuelle, en utilisant le format, …)
2. Cliquer sur la donnée recherchée
3. Récupérer la liste des points d’entrée. Depuis le point d’entrée choisi, relancer le Scan. Pour information, il est possible d’utiliser un critère d’inclusion pour scanner uniquement la donnée correspondante.
4. Vous pouvez également exclure la donnée des points d’entrée qui ne “devraient” pas la scanner (*“Bouton Actions” > “Exclure/Gérer les exclusions”*)
![Trouver les points d'entrée et gérer les exclusions](/assets/ressources_find_entrypoint.png)
5. Une popup s’ouvre alors pour choisir le point d’entrée où appliquer l’exclusion. Seuls les points d’entrée où aucun autre critère d’exclusion (format, dossier, schema) n'excluent pas déjà la donnée sont proposés.
6. Sélectionner le point d'entrée correspondant et cliquer sur Exclure.
![Exclure d'un point d'entrée](/assets/ressources_exclusion_from_entrypoint.png)

## Exporter les résultats d’une requête du scan {#export}

Pour exporter au format csv le résultat de la dernière requête d’un point d’entrée : 

1. Sélectionner le point d’entrée de cette requête dans les filtres 
2. Cliquer sur le bouton *Exporter la recherche*
![Export d'une requête](/assets/ressources_search_export.png)
3. Un fichier CSV est généré contenant toutes les colonnes peu importe celles qui sont activées dans les *Paramètres avancés*.
![Tableau exporté](/assets/ressources_export_table.png)
