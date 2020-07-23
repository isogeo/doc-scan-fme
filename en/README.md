# Scan FME Isogeo - Installation et utilisation

## Historique

Développé en 2013 par Isogeo, le service Isogeo Worker a commencé à être déployé à la fin de la même année et surtout à partir de début 2014.

Basé sur lETL FME, édité par Safe Software, il permet de lire un très grand nombre de formats de données géographiques et den extraire la plupart des informations techniques que lon sattend à voir dans une fiche de métadonnées.

![Logo Safe Software - FME](/assets/logo_safe_fme.png)

## Architecture

![Schéma de larchitecture vulgarisée](/assets/architecture.png "Architecture globale du service de scan Isogeo")

## Relations logiques

* un groupe de travail peut installer plusieurs services.
* un service ne peut être lié quà un seul groupe de travail.
* une licence FME peut être utilisée par plusieurs services.

## Guide vidéo

{% youtube %}
<https://www.youtube.com/watch?v=gLCSeQZMqvs>
{% endyoutube %}

----

Date de la dernière mise à jour de cette documentation : **{{ gitbook.time | date("DD/MM/YYYY") }}**.
