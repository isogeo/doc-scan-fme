---
description: Mise à jour du service client du Scan FME (Isogeo)
---

# Mise à jour

Les mises à jour sont effectuées automatiquement par Isogeo lors de la mise en production d'une nouvelle version.

Vous pouvez consulter les notes de versions dans le détail du service.

![Consulter les notes de version du service Isogeo](/assets/versions_notes.png)

Dans le détail, la mise à jour automatique du client du Scan (Isogeo Worker) suit les étapes suivantes :

1. Le client requête régulièrement https://scan.isogeo.com/workers-api/v1/about en s'authentifiant avec ses identifiants spécifiques.
2. Si la version courante du client est inférieure à celle retournée par la requête */about*, il télécharge l'archive du code à l'adresse https://scan.isogeo.com/workers-api/v1/download-archive (toujours en s'authentifiant).
3. Il dézippe le contenu de l'archive.
4. Il supprime tous les fichiers du répertoire d'installation sauf le dossier bin contenant les exécutables (node et nssm).
5. Il écrit tous les fichiers de l'archive (à l'exception du dossier bin) dans le dossier courant.
6. Il force son propre arrêt puis redémarre automatiquement comme il s'agit d'un service.

Remarques :

* Les identifiants sont spécifiques à chaque client Isogeo Worker et sont renseignés dans le fichier de connexion à la racine du répertoire d'installation (`connection.json`).
* Nous mettons également à jour les exécutables du dossier *bin* mais ceci de manière exceptionnelle comme pour une montée de version de NodeJS par exemple. Dans ce cas, le dossier *bin* est lui aussi supprimé et remplacé.