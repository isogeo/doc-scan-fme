# Déploiement du service

## Téléchargement du service

Le service Isogeo est généré à partir de notre plate-forme pour chaque groupe de travail et possède ses propres identifiants.

Pour le récupérer, connectez-vous sur https://app.isogeo.com avec votre compte et rendez-vous dans la section Administration > Applications > Scan FME.

> Astuce : pour accéder directement à l&apos;interface d&apos;administration du scan : https://app.isogeo.com/admin/isogeo-worker

Si aucun service n&apos;est actif, vous êtes invité à générer votre service en lui donnant un nom simple. Par exemple, celui de la machine ou de son utilisateur.

Vous pouvez également installer un nouveau service en sélectionnant <i class="fa fa-plus"></i> `Ajouter` dans le menu <i class="fa fa-reorder"></i>.

![Scan - Menu](/assets/scanFME/scanFME_menu.png "Menu de l&apos;interface web du Scan FME")

Une fois nommé, vous pouvez télécharger le service.

![Nouveau service](/assets/scanFME/scanFME_install_new_service_download.png "Nommer le nouveau service et cliquer sur télécharger")

## Installation du service

1.	Décompresser l’archive (zip) téléchargée dans le dossier `C:\Program files\Isogeo`. S&apos;il n&apos;existe pas, il faut le créer.

    ![Contenu de l&apos;archive du service](/assets/scanFME/scanFME_install_content.png "Décompresser l&apos;archive zip du service dans le dossier Isogeo")

2.	Ouvrir le dossier`daemon`;
3.	Faire un clic droit sur `install.bat`, puis `Exécuter en tant qu’administrateur`

    ![Installer avec des droits d&apos;administrateur](/assets/scanFME/scanFME_install_RunAsAdmin.png "Installer le service avec les droits d&apos;administration")

Une console Windows s’ouvre alors, indiquant que l’installation et le démarrage du service sont en cours puis se ferme automatiquement. Si la fenêtre ne se ferme pas et qu’un message d’erreur apparaît, revérifier les prérequis. Si le problème persiste, [contacter le support](../../../support/index.html).

## Vérifier l&apos;installation du service

1. Ouvrir la console des services Windows (cliquez sur « Démarrer », rechercher « services »).

    ![Ouvrir les services](/assets/scanFME/scanFME_install_servicesWindows.png "Accéder au gestionnaire de services de Windows")

2. Si l’installation du Service Isogeo s’est correctement déroulée, un service nommé `Isogeo Worker` avec l’état `En cours d&apos;exécution` (ou "Démarré" sous W7) se trouve dans la liste.

    ![Service Isogeo Worker démarré](/assets/scanFME/scanFME_install_ServiceRunning.png "Le service Isogeo Worker est bien démarré")

Si ce service n&apos;apparaît pas, tenter de rafraîchir la liste (F5).<br />S&apos;il n&apos;apparaît toujours pas, essayer de nouveau l’installation.

## Configuration du service

Le service **doit être lancé par l&apos;utilisateur Windows dédié isogeo** ([voir les pré-requis](prerequisites.html#compte-utilisateur)). Or après l&apos;installation, c&apos;est le compte administrateur local qui en est "maître".

1. Ouvrir les propriétés du service (clic droit>propriétés),
2. Dans l’onglet `Connexion`, choisir l’option `Ce compte` et indiquer les identifiants du compte utilisateur `isogeo`.

    ![Ouvrir les services](/assets/scanFME/scanFME_install_service_RunAs.png "Accéder au gestionnaire de services de Windows")

3. Cliquer sur `OK`, une fenêtre indique qu&apos;il est nécessaire de redémarrer le service pour prendre en compte le changement,
4. Clic droit sur le service > `Redémarrer`

L’installation est à présent terminée :) !

## Retour à l’application Isogeo

Une fois l’installation effectuée, revenez sur votre navigateur et cliquez sur « Aller à l’application ». Normalement vous devez voir un point vert dans l’en-tête de l’application, cela veut dire que la communication entre le service que vous venez d’installer et la Plateforme Isogeo est établie !

Si le point est rouge, utilisez la fonction « <i class="fa fa-refresh"></i> Rafraîchir » disponible via le menu en haut à droite <i class="fa fa-reorder"></i>.

Si rien ne change au bout de 5 minutes, [contacter le support](../../../support/index.html).
