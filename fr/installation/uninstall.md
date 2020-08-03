---
description: Désinstallation du service client du Scan FME (Isogeo)
---

# Désinstallation du service de scan {#uninstall}

La suppression d'un service Isogeo s'effectue en deux étapes dépendantes dont l'ordre d’exécution n'est pas important. Cependant, si l'une des deux étapes n'est pas réalisée, cela peut amener des dysfonctionnements futurs lors de l'utilisation de l'application.

## Désinscription du service dans Isogeo

1. Sur Isogeo, rendez-vous dans l'application Scan FME (menu `Administration` → `Applications / Scan FME`) ou directement en suivant [ce lien](https://app.isogeo.com/admin/isogeo-worker) ;

2. Cliquez sur le service que vous voulez supprimer ;

3. Cliquez sur le bouton rouge de suppression.

## Suppression du service installé sur le serveur

Plusieurs paramètres sont potentiellement spécifiques à votre installation.

1. À l'aide de votre explorateur Windows, naviguez vers le répertoire du service (selon nos recommandations, ce devrait être `C:\Program Files\Isogeo`) ;

2. Ouvrez le dossier *daemon* ;

3. Faites un clic droit sur le fichier uninstall.bat, puis `Exécuter en tant qu’administrateur`. Une fenêtre devrait s'ouvrir puis se fermer automatiquement.

4. Supprimez l'ensemble du répertoire du service.

<!-- ### Suppression forcée du service dans Windows {#remove_cmd}

Selon la configuration de l'environnement Windows, il se peut qu'il faille supprimer le service via une commande en mode administrateur :

```cmd
sc delete "Isogeo Worker - IdentifiantduGroupedeTravail"
```

![Scan - Supp](/assets/service_remove_cmd.png)

Puis redémarrer la machine. -->
