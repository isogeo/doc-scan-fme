# Configuration

Pour pouvoir utiliser le Scan FME, il faut installer un service Windows nommé Isogeo Worker sur une machine, virtuelle ou physique, de votre organisme respectant les pré-requis.

## Système d’exploitation

Même sil est possible d’installer le service Isogeo sur un poste dutilisateur, **il est fortement recommandé d’utiliser un serveur** pour des questions de performances, d’accès et de disponibilité.

Les versions de Windows supportées sont (les versions  en **gras** sont recommandées) :

* Windows Server 2003 SP2, 2008, **2008 R2**, **2012** et **2012 R2** ;
* Windows XP SP3 32 bits, Vista SP2, **7**, 8, **8.1**, **10**.

## Compte utilisateur

Vous devez créer un compte utilisateur Windows permettant :

* dexécuter FME Desktop sur le poste où est installé le service Isogeo,
* décrire dans le répertoire dinstallation du service Isogeo,
* d’accéder aux ressources réseaux nécessaires pour lire vos données SIG.

Il est recommandé de créer un nouveau compte utilisateur de niveau administrateur local intitulé Isogeo ayant les droits adéquats sur les données.