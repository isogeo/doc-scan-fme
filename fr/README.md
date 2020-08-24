---
description: Présentation du Scan FME Isogeo
---

# Scan FME Isogeo - Installation et utilisation {#presentation}

## Historique {#history}

Développé en 2013 par Isogeo, le service Isogeo Worker a commencé à être déployé à la fin de la même année et surtout à partir de début 2014.

Basé sur l'ETL FME, édité par Safe Software, il permet de lire un très grand nombre de formats de données géographiques et d'en extraire la plupart des informations techniques que l'on s'attend à voir dans une fiche de métadonnées.

![Logo Safe Software - FME](/assets/logo_safe_fme.png)

Lors de sa refonte en 2020, une nouvelle architecture a été mise en place ne nécéssitant plus l'ouverture d'un port spécifique pour la communication. Une nouvelle interface, et une API dédiée ont également été mises en place.

## Architecture {#architecture}

![Schéma de larchitecture vulgarisée](/assets/architecture.png "Architecture globale du service de scan Isogeo")

## Relations logiques {#relations}

* un groupe de travail peut installer plusieurs services.
* un service ne peut être lié qu'à un seul groupe de travail.
* une licence FME peut être utilisée par plusieurs services.

<!-- ## Guide vidéo {#video}


{% youtube %}
<https://www.youtube.com/watch?v=gLCSeQZMqvs>
{% endyoutube %}

---- -->

Date de la dernière mise à jour de cette documentation : **{{ gitbook.time | date("DD/MM/YYYY") }}**.
