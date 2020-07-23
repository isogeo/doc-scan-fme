# Deploying the service

## Downloading the service

Each Isogeo service is generated from our platform, and has its own identifiers.

To retrieve the service, log in to your account at http://app.isogeo.com, then go to Administration > Applications > Scan FME, or click here.

The first time, you will be prompted to create your first service and give it a simple name, such as the name of your machine or its user.

After confirming, you are given a download link. Click this link to download the service to be installed.

![New service](/assets/install_new_service_download.png "Nommer le nouveau service et cliquer sur télécharger")

## Installing the service

1.	Unzip the downloaded (zip file) archive to a folder of your choice on your machine. You can choose any location for this folder, but make sure you remember it, and do not change it once you have completed the installation; otherwise you may need to start over. For example, choose folder C:\Program files\Isogeo (provided you have the necessary permissions).

    ![Contenu de larchive du service](/assets/install_content.png "Décompresser larchive zip du service dans le dossier Isogeo")

2.	Open the "daemon" folder.

3.	Right-click on "install.bat," then choose "Run as administrator."

    ![Installer avec des droits dadministrateur](/assets/install_RunAsAdmin.png "Installer le service avec les droits dadministration")

A pop-up window will indicate that the service is being installed then started. This window will close automatically.

If it does not close and you get an error message, [contact our support team](/en/support/README.html).


## Check service installation

1. Open the Windows Management Console (click on "Start" then enter "services" in the search bar).

    ![Ouvrir les services](/assets/install_servicesWindows.png "Accéder au gestionnaire de services de Windows")

2. A window containing all the Windows services is displayed. If the Isogeo service was correctly installed, the list will include the "Isogeo Service" with the "Started" status.

    ![Service Isogeo Worker démarré](/assets/install_ServiceRunning.png "Le service Isogeo Worker est bien démarré")

If the service is not listed, refresh the list (right-click > Refresh). If it is still not listed, repeat the installation procedure by right-clicking the “install.bat” file, and then choosing “Run as administrator” (see also Installing the service - step 3).

## Setting up the service

To be able to access all the resources required for the service to run (data, FME solution, etc.), you must run the service from a user account with the necessary permissions (see User account).


1. Go to the service properties (right-click > Properties),
2. then click on the “Log On” tab. Choose "This account", and enter your user account credentials (see Prerequisites).

    ![Ouvrir les services](/assets/install_service_RunAs.png "Accéder au gestionnaire de services de Windows")

3. Once you have entered the account, click “OK”. You will be prompted to restart the service to accept the change. To follow this instruction, right-click on the service and choose “Restart”.


The last column in the service should now match the account credentials you just entered.

## Return to the Isogeo application.

Once you have completed the installation, go back to your browser and click on "Go to the application." You should see a green indicator light in the application header. This means that communication has been established between the service you just installed and the Isogeo Platform.

If the indicator light is red, choose "Refresh" in the menu to the right of this indicator.

If the indicator stays red for more than 5 minutes, contact our support team.
