---
description: Présentation générale des prérequis pour l'installation du Scan FME Isogeo
---

# Prérequis {#requirements}

Pour pouvoir utiliser le Scan FME, il faut installer un service Windows nommé Isogeo Worker sur un serveur Windows (virtuel ou physique), de votre organisme respectant les pré-requis suivants.

* Isogeo
  * un groupe de travail autorisé à utiliser le module Scan FME
  * un accès administrateur au groupe de travail pour télécharger le service et lancer les scans via <https://app.isogeo.com>

* [Serveur](installation/server.md)
  * Windows Server 2003 SP2, 2008, 2008 R2, **2012**, **2012 R2**, **2016** et **2019** ;
  * Compte utilisateur Windows

* [Réseau](installation/network.md)
  * Accès en https aux domaines qui se terminent par isogeo.com (`*.isogeo.com`)
  * Configuration du proxy

* [Logiciels](installation/softwares.md)  
  * FME Desktop 2018
  * ArcGIS Desktop pour les formats Esri (Geodatabases)
