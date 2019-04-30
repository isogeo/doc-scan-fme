---
description: Présentation du Scan FME Isogeo
---

# Scan FME Isogeo - Installation et utilisation {#presentation}

## Historique {#history}

Développé en 2013 par Isogeo, le service Isogeo Worker a commencé à être déployé à la fin de la même année et surtout à partir de début 2014.

Basé sur l&apos;ETL FME, édité par Safe Software, il permet de lire un très grand nombre de formats de données géographiques et d&apos;en extraire la plupart des informations techniques que l&apos;on s&apos;attend à voir dans une fiche de métadonnées.

![Logo Safe Software - FME](/assets/logo_safe_fme.png)

## Architecture {#architecture}


![Schéma de l&apos;architecture vulgarisée](/assets/scanFME_architecture.png "Architecture globale du service de scan Isogeo")

## Relations logiques {#relations}


* un groupe de travail peut installer plusieurs services.
* un service ne peut être lié qu&apos;à un seul groupe de travail.
* une licence FME peut être utilisée par plusieurs services.

## Guide vidéo {#video}


{% youtube %}
<https://www.youtube.com/watch?v=gLCSeQZMqvs>
{% endyoutube %}

----

Date de la dernière mise à jour de cette documentation : **{{ gitbook.time | date("DD/MM/YYYY") }}**.
