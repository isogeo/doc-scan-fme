# Configuration

Pour pouvoir utiliser le Scan FME, il faut installer un service Windows nommé Isogeo Worker sur une machine, virtuelle ou physique, de votre organisme respectant les pré-requis.

## Système d’exploitation

Même s&apos;il est possible d’installer le service Isogeo sur un poste d&apos;utilisateur, **il est fortement recommandé d’utiliser un serveur** pour des questions de performances, d’accès et de disponibilité.

Les versions de Windows supportées sont (les versions  en **gras** sont recommandées) :

* Windows Server 2003 SP2, 2008, **2008 R2**, **2012** et **2012 R2** ;
* Windows XP SP3 32 bits, Vista SP2, **7**, 8, **8.1**, **10**.

## Compte utilisateur

Vous devez créer un compte utilisateur Windows permettant :

* d&apos;exécuter FME Desktop sur le poste où est installé le service Isogeo,
* d&apos;écrire dans le répertoire d&apos;installation du service Isogeo,
* d’accéder aux ressources réseaux nécessaires pour lire vos données SIG.

Il est recommandé de créer un nouveau compte utilisateur de niveau administrateur local intitulé Isogeo ayant les droits adéquats sur les données.

___

## Configuration réseau et sécurité

Si votre serveur est connecté à Internet via un réseau d’entreprise soumis à des politiques de sécurité (cas le plus fréquent), vous devez vous assurer que :

* votre navigateur peut accéder aux différents sites Internet gérés par Isogeo (tous nos sites ont des domaines qui se terminent par isogeo.com et utilisent le protocole sécurisé HTTPS) tel que [https://app.isogeo.com](https://app.isogeo.com)
* votre système d’exploitation peut se connecter au port **5671** des domaines **daemons-mq.isogeo.com** et **daemons.isogeo.com**, tous deux sur l&apos;IP *65.52.153.255*, à l&apos;aide du **protocole TCP sécurisé**.

Il faut vérifier auprès de vos éventuels pare-feu, proxy et fichiers hosts que le filtre par domaine ou  IP autorise bien les communications. Généralement vous obtiendrez ces informations auprès de votre service informatique.
