# Uninstalling the scan service

Removing an Isogeo service takes two interdependent processes that can be done in any order. Note that failure to perform one of these two steps may lead to malfunctions when using the application.

## Deregistering from the service in Isogeo

1. In Isogeo, go to the Scan FME application (menu `Administration` → `Applications / Scan FME`) or click [this link](https://app.isogeo.com/admin/isogeo-worker).

2. In the interface, enable delete mode by clicking on `Delete` in the menu at the top right.

3. Click on the service you want to remove (or on the Validate icon to cancel).

4. Once you have deleted the service, click on Validate.

If you no longer have a registered service, you will be automatically prompted to download a new one.

## Deleting an installed service

There are potentially several settings that are specific to your installation.

1. Go to the folder containing the service in Windows Explorer (if you followed our recommendation, it will be `C:\Program Files\Isogeo`).

2. Open the "daemon" folder.

3. Right-click on "uninstall.bat," then choose "Run as administrator." A pop-up window opens and then closes automatically.

4. Delete the entre folder containing the service.
