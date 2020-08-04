---
description: Installation du service client du Scan FME (Isogeo)
---

# Déploiement du service {#deployment}

## Téléchargement du service {#download}

Le service Isogeo est généré à partir de notre plate-forme pour chaque groupe de travail et possède ses propres identifiants.

Pour le récupérer, connectez-vous sur https://app.isogeo.com avec votre compte et rendez-vous dans la section Administration > Applications > Scan FME.

> Astuce : pour accéder directement à l'interface d'administration du scan : https://app.isogeo.com/admin/isogeo-worker

Si aucun service n'est installé, vous pouvez créer votre premier service via l'interface ci-dessous en cliquant sur Paramètres puis *Créer un nouveau service*.

!["Création du service depuis l'interface"](/assets/interface_first_installation.png)

L'interface, vous permet ensuite de télécharger l'installeur.

!["Télécharger l'installeur"](/assets/interface_first_installation_2.png)

## Installation du service {#installation}

1.	Décompresser l’archive (zip) téléchargée dans le dossier `C:\Program files\Isogeo`.

    ![Contenu de l'archive du service](/assets/install_content.png "Décompresser l'archive zip du service dans le dossier Isogeo")

2.	Ouvrir le dossier`daemon`;
3.	Faire un clic droit sur `install.bat`, puis `Exécuter en tant qu’administrateur`

    !["Installer le service avec les droits d'administration"](/assets/install_RunAsAdmin.png)

Une console Windows s’ouvre alors, indiquant que l’installation et le démarrage du service sont en cours puis se ferme automatiquement. Si la fenêtre ne se ferme pas et qu’un message d’erreur apparaît, revérifier les prérequis. Si le problème persiste, [contacter le support](/support/support.md).

## Vérifier l'installation du service {#verification}

1. Ouvrir la console des services Windows (cliquez sur « Démarrer », rechercher « services »).
2. Si l’installation du Service Isogeo s’est correctement déroulée, un service nommé `Isogeo Worker - IdentifiantduGroupedeTravail` avec l’état `En cours d'exécution` se trouve dans la liste.

Si ce service n'apparaît pas, tenter de rafraîchir la liste (F5). S'il n'apparaît toujours pas, essayer de nouveau l’installation.

## Configuration du service {#configuration}

Le service **doit être lancé par l'utilisateur Windows dédié isogeo** ([voir les pré-requis](server.md#user)). Or après l'installation, c'est le compte administrateur local qui en est "maître".

1. Ouvrir les propriétés du service (clic droit>propriétés)

 !["Ouvrir les propriétés du service"](/assets/install_service_properties.png)

2. Dans l’onglet `Connexion`, choisir l’option `Ce compte` et indiquer les identifiants du compte utilisateur `isogeo`.

!["Accéder au gestionnaire de services de Windows"](/assets/install_service_RunAs.png)

3. Cliquer sur `OK`, une fenêtre indique qu'il est nécessaire de redémarrer le service pour prendre en compte le changement,
4. Clic droit sur le service > `Redémarrer`

L’installation est à présent terminée :) !

## Retour à l’application Isogeo {#app}

Une fois l’installation effectuée, revenez sur votre navigateur et sur l'interface du Scan FME.

Si l'installation est réussie, le service installé prend automatiquement le nom de votre serveur.
La version et l'état "Connecté" s'affichent également en vert.

En cliquant sur le nom du service, vous constaterez que les informations sur la configuration du serveur et le chemin vers FME sont remontées.

!["Installation réussie"](/assets/install_service_done.png)

Si le point est rouge, actualisez la page, la communication est peut-être bloquée par un proxy. 

## Configurer le proxy {#config_proxy}

Le client peut être utilisé derrière un proxy d'entreprise. Pour cela, il faut créer un fichier *proxy.json* à la racine du répertoire du service, et indiquer l'URL du proxy. Indiquer également un utilisateur et son mot de passe si une authentification au proxy est nécéssaire.

Exemple :

```json
{
  "httpsProxy": "http://user:pass@proxy:8080"
}
```

Si la connexion n'est toujours pas effective, [contacter le support](/support/support.md).