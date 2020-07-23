---
description: Paramètres de connexion réseau du service client du Scan FME (Isogeo)
---

# Configuration réseau et sécurité des échanges {#network_configuration}

Le Scan FME utilise le protocole HTTPS.

## Connectivité {#connectivity}

Pour que le client du Scan FME puisse communiquer correctement avec les serveurs d'Isogeo, il faut s'assurer que :

* votre navigateur peut accéder aux différents sites Internet gérés par Isogeo (tous nos sites ont des domaines qui se terminent par isogeo.com et utilisent le protocole sécurisé HTTPS) tel que [https://app.isogeo.com](https://app.isogeo.com)

* votre système d’exploitation peut se connecter au port **443** vers le domaine **scan.isogeo.com**, à l'aide du **protocole HTTPS sécurisé**.

Il faut vérifier auprès de vos éventuels pare-feu, proxy et fichiers hosts qu'ils autorisent bien les communications. Généralement vous obtiendrez ces informations auprès de votre service informatique.

----

## Sécurité {#security}

### Sécurisation des accès et des transmissions

* Le service Isogeo (composant client) communique avec la plateforme Isogeo lors de certaines opérations d’administration (scan des données géographiques et synchronisation). L’authentification se fait par identifiants et la communication est chiffrée entre l’agent et la plateforme (SSL).

* La communication entre l’agent et la plateforme est initiée depuis l’agent. Il n’est pas nécessaire d’ouvrir de ports entrants spécifiques.

### Contrôle de l’accès aux données lors du recensement automatique

* L’accès aux données s’effectue par l’intermédiaire du logiciel [FME](http://www.safe.com/fme/fme-technology/fme-desktop/overview/)

* L’accès aux données est entièrement configurable par l’organisme. Il suffit de donner accès aux bases de données et aux répertoires à l'utilisateur de domaine qui lance le service.

* L’accès aux données dépend du type de stockage des données :
  * Système de Gestion de Base de Données (SGBD) : tous systèmes d'exploitation.
  * Fichiers : il faut pouvoir mettre à disposition du service un partage de type Windows (protocole SMB). De plus, il est préférable qu'ils soient hébergés sur un OS de type serveur.

* L'accès aux données est en lecture seule, mais certains fournisseurs d’accès aux données requièrent un accès en lecture/écriture. La donnée géographique n’est pas modifiée, mais des mises à jour de fichiers d’index ou d’informations techniques peuvent demander des accès en écriture.

* L’agent ne stocke pas d’informations pour lui-même. Cependant il peut être amené à générer des fichiers temporaires potentiellement volumineux dont il assure le nettoyage de façon automatique.
