# Désinstallation du service de scan

La suppression d&apos;un service Isogeo s&apos;effectue en deux étapes dépendantes dont l&apos;ordre d’exécution n&apos;est pas important. Cependant, si l&apos;une des deux étapes n&apos;est pas réalisée, cela peut amener des dysfonctionnements futurs lors de l&apos;utilisation de l&apos;application.

## 1. Désinscription du service dans Isogeo

1. Sur Isogeo, rendez-vous dans l&apos;application Scan FME (menu `Administration` → `Applications / Scan FME`) ou directement en suivant [ce lien](https://app.isogeo.com/admin/isogeo-worker) ;

2. Dans l&apos;interface, activez le mode de suppression en cliquant sur `Supprimer` dans le menu en haut à droite ;

3. Cliquez sur le service que vous voulez supprimer (ou sur l&apos;icône de validation pour annuler) ;

4. Une fois le service supprimé, cliquez sur valider.

Si vous n&apos;avez plus de service d&apos;inscrit, vous serez automatiquement amené(e) à en télécharger un nouveau.

## 2. Suppression du service installé sur l'infrastructure du client

Plusieurs paramètres sont potentiellement spécifiques à votre installation.

1. À l&apos;aide de votre explorateur Windows, naviguez vers le répertoire du service (selon nos recommandations, ce devrait être `C:\Program Files\Isogeo`) ;

2. Ouvrez le dossier daemon ;

3. Faites un clic droit sur le fichier uninstall.bat, puis `Exécuter en tant qu’administrateur`. Une fenêtre devrait s&apos;ouvrir puis se fermer automatiquement.

4. Supprimez l&apos;ensemble de répertoire du service.

### Suppression forcée du service dans Windows {#remove_cmd}

Selon la configuration de l'environnement Windows, il se peut qu'il faille supprimer le service via une commande en mode administrateur :

```cmd
sc delete "Isogeo Worker"
```

![Scan - Supp](/assets/scanFME/scanFME_service_remove_cmd.png)

Puis redémarrer la machine.
