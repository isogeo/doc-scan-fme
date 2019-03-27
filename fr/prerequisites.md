# Configuration

Pour pouvoir utiliser le Scan FME, il faut installer un service Windows nommé Isogeo Worker sur un serveur Windows (virtuel ou physique), de votre organisme respectant les pré-requis suivants.

* [Serveur](installation/server.md)
    * Windows Server 2003 SP2, 2008, **2008 R2**, **2012** et **2012 R2** ;
    * Compte utilisateur Windows administrateur local
* [Réseau](installation/network.md)    
    * Accès en https aux domaines qui se terminent par isogeo.com (`*.isogeo.com`)
    * Ouverture du port **5671** vers les domaines **daemons-mq.isogeo.com** et **daemons.isogeo.com**, tous deux sur l&apos;IP *65.52.153.255*, à l&apos;aide du **protocole TCP sécurisé**.
* [Logiciels](installation/softwares.md)  
    * FME Desktop 2013 SP4 à 2016 SP1
