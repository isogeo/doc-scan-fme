---
description: Présentation générale des prérequis pour l'installation du Scan FME Isogeo
---

# Prérequis {#requirements}

Pour pouvoir utiliser le Scan FME, il faut installer un service Windows nommé Isogeo Worker sur un serveur Windows (virtuel ou physique), de votre organisme respectant les pré-requis suivants.

* Isogeo
  * un groupe de travail autorisé à utiliser le module Scan FME
  * un accès administrateur au groupe de travail pour télécharger le service et lancer les scans via <https://app.isogeo.com>

* [Serveur](installation/server.md)
  * Windows Server 2003 SP2, 2008, **2008 R2**, **2012** et **2012 R2** ;
  * Compte utilisateur Windows

* [Réseau](installation/network.md)
  * Accès en https aux domaines qui se terminent par isogeo.com (`*.isogeo.com`)
  * Ouverture du port **5671** vers les domaines **daemons-mq.isogeo.com** et **daemons.isogeo.com**, tous deux sur l&apos;IP *65.52.153.255*, à l&apos;aide du **protocole TCP sécurisé**.

* [Logiciels](installation/softwares.md)  
  * FME Desktop 2016 SP1
  * éventuellement ArcGIS pour les formats Esri spécifiques
