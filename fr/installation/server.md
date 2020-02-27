---
description: Configuration du serveur Windows du service client du Scan FME (Isogeo)
---

# Configuration {#configuration_server}

Pour pouvoir utiliser le Scan FME, il faut installer un service Windows nommé Isogeo Worker sur une machine, virtuelle ou physique, de votre organisme respectant les pré-requis.

## Système d’exploitation {#os}

Même s&apos;il est possible d’installer le service Isogeo sur un poste d&apos;utilisateur, **il est fortement recommandé d’utiliser un serveur** pour des questions de performances, d’accès et de disponibilité.

Les versions de Windows supportées sont (les versions  en **gras** sont recommandées) :

* Windows Server 2003 SP2, 2008, 2008 R2, **2012**, **2012 R2**, **2016** et **2019** ;
* Windows XP SP3 32 bits, Vista SP2, **7**, 8, **8.1**, **10**.

## Compte utilisateur {#user}

Vous devez créer un compte utilisateur Windows permettant :

* d&apos;exécuter FME Desktop sur le poste où est installé le service Isogeo,
* d&apos;écrire dans le répertoire d&apos;installation du service Isogeo,
* d’accéder aux ressources réseaux nécessaires pour lire vos données SIG.

Il est recommandé de créer un nouveau compte utilisateur de niveau administrateur local intitulé Isogeo ayant les droits adéquats sur les données.