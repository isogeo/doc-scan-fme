# Configuration

Pour pouvoir utiliser le Scan FME, il faut installer un service Windows nommé Isogeo Worker sur une machine, virtuelle ou physique, de votre organisme respectant les pré-requis suivants.

* Windows Server 2003 SP2, 2008, **2008 R2**, **2012** et **2012 R2** ;
* Compte utilisateur Windows administrateur local
* Accès en https aux domaines qui se terminent par isogeo.com
* Ouverture des ports **5671** des domaines **daemons-mq.isogeo.com**,
    **daemons.isogeo.com**, tous deux sur l&apos;IP *65.52.153.255*, à l&apos;aide du **protocole TCP sécurisé**.
* FME Desktop