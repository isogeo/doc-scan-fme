---
description: Paramètres de connection réseau du service client du Scan FME (Isogeo)
---

# Configuration réseau et sécurité des échanges

Le Scan FME utilise le protocole [AMQP(S)](https://fr.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol), dans l'implémentation faite par [RabbitMQ](https://fr.wikipedia.org/wiki/RabbitMQ).

## Connectivité

Pour que le client du Scan FME puisse communiquer correctement avec les serveurs d'Isogeo, il faut s'assurer que :

* votre navigateur peut accéder aux différents sites Internet gérés par Isogeo (tous nos sites ont des domaines qui se terminent par isogeo.com et utilisent le protocole sécurisé HTTPS) tel que [https://app.isogeo.com](https://app.isogeo.com)

* votre système d’exploitation peut se connecter au port **5671** des domaines **daemons-mq.isogeo.com** et **daemons.isogeo.com**, tous deux sur lIP *65.52.153.255*, à laide du **protocole TCP sécurisé**.

Il faut vérifier auprès de vos éventuels pare-feu, proxy et fichiers hosts que le filtre par domaine ou IP autorise bien les communications. Généralement vous obtiendrez ces informations auprès de votre service informatique.

----

## Sécurité

### Sécurisation des accès et des transmissions

* Le service Isogeo (composant client) communique avec la plateforme Isogeo lors de certaines opérations d’administration (scan des données géographiques et synchronisation). L’authentification se fait par identifiants et la communication est chiffrée entre l’agent et la plateforme (SSL).

* La communication entre l’agent et la plateforme est initiée depuis l’agent. Il n’est pas nécessaire d’ouvrir de ports entrants spécifiques.

* Il est en revanche indispensable d’autoriser les communications entrantes et sortantes sur le port TCP 5671.

### Contrôle de l’accès aux données lors du recensement automatique

* L’accès aux données s’effectue par l’intermédiaire du logiciel [FME](http://www.safe.com/fme/fme-technology/fme-desktop/overview/)

* L’accès aux données est entièrement configurable par l’organisme. Il suffit d’indiquer à l’exécutable les bases de données et les répertoires auxquels il peut accéder.

* L’accès aux données dépend du type de stockage des données :
  * Système de Gestion de Base de Données (SGBD) : tous systèmes dexploitation.
  * Fichiers : il faut pouvoir mettre à disposition du service un partage de type Windows (protocole SMB). De plus, il est préférable quils soient hébergés sur un OS de type serveur.

* Laccès aux données est en lecture seule, mais certains fournisseurs d’accès aux données requièrent un accès en lecture/écriture. La donnée géographique n’est pas modifiée, mais des mises à jour de fichiers d’index ou d’informations techniques peuvent demander des accès en écriture.

* L’agent ne stocke pas d’informations pour lui-même. Cependant il peut être amené à générer des fichiers temporaires potentiellement volumineux dont il assure le nettoyage de façon automatique.
