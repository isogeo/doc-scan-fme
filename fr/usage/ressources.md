---
description: Consulter la liste et les informations des ressources scannées à l'aide du Scan Isogeo.
---

# Page Ressources

La page `Ressources` constitue l'inventaire de l'ensemble des ressources scannées. 

Cette page est composée de deux onglets : 

* un onglet `Ressources` listant toutes les ressources scannées dans un tableau selon des critères de filtre ;
* un onglet `Paramètres avancés` permettant de fixer des paramètres et des conditions d’affichage de la liste de ressources. 
  
## Onglet Ressources {#ressources}

Au chargement de la page, le tableau présente l'ensemble des ressources (données et services) dont le scan a abouti au moins une fois. On ne retrouve donc pas les données en erreur ou celles retirées de la liste. En effet, si une donnée n'est plus présente dans votre patrimoine, vous pouvez la retirer de la liste une fois sa fiche de métadonnée supprimée du catalogue (cf. [Identifier les ressources qui ne sont plus détectées dans le patrimoine pour les supprimer du catalogue](usage/ressources_usages.md#identify_data_to_delete)). 

![Retirer de la liste les données](/assets/exclusion_red_data_from_inventory.png)

Vous pouvez  filtrer les resources selon les critères suivants (en **gras** les critères acceptant la recherche selon plusieurs valeurs de filtre) : 

* Recherche textuelle : filtrer sur toutes les ressources dans lesquelles on retrouve la chaîne de caractère recherchée dans le nom. Par exemple en tapant "plu" ; ![Rechercher une chaine de caractère](/assets/ressources_search_data.png)
* **Format de la ressource** (ex : esrigdb, jp2, EMS etc.) ;
* **Dernier statut remonté par le scan** (inchangé, modifié, structure modifiée, déplacé, nouveau, ignoré) ;
![Filtrer sur un ou plusieurs statut](/assets/ressources_status_filter.png)
* **Point d'entrée** : choisir les points d'entrée dont vous voulez afficher les ressources associées ;
* Date du *dernier Scan* ou *de la dernière mise à jour de la métadonnée* : sélectionner la période correspondante à la date recherchée.  

Vous pouvez également exporter la recherche en CSV à l'aide du bouton correspondant. Celui-ci contient l'ensemble des informations affichables dans le tableau.

## Onglet Paramètres avancés {#advanced_parameters}

![Page des Paramètres avancés](/assets/ressources_advanced_parameters.png)

### Conditions d'affichage des ressources {#conditions}

L'onglet *Ressources* présente toutes les ressources dont les conditions respectent les paramètres avancés. Les conditions sont réinitialisées à chaque rechargement de la page *Ressources*.
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
* Différence d'entités : différence du nombre d'entités détectées sur les données modifiées lors du dernier scan
* Différence d'entités (%) : pourcentage de cette différence par rapport au nombre total d'entités détectées lors du scan précédent
* Différence d'attributs : différence du nombre d'attributs détectés sur des données dont la structure a été détectée comme modifiée lors du dernier scan
* Attributs ajoutés et supprimés : colonnes permettant d'afficher le nombre d'attributs ajoutés et le nombre d'attributs supprimés sur des données dont la structure a été modifiée
* Lien vers la fiche : lien vers la fiche dans l'interface d'administration du catalogue
* Actions : bouton permettant de retirer des ressources de la liste ou de gérer les exclusions de leurs points d'entrée

Nous vous invitons à découvrir quelques [cas d'usage](/usage/ressources_usages.md) de cette fonctionnalité en page suivante. 