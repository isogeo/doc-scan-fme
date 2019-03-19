# Standard installation

Classic installation process for standard users, through the stable channel of QGIS plugins.

## Check requirements {#requirements}

In QGIS, check network settings \(proxy...\) opening menu _Settings_ &gt; _Options..._:

!["Check QGIS connection settings"](/assets/qgis_install_network_en.png)

## Install the extension {#install}

Open the plugin manager, search for _Isogeo_ and clic on "Install plugin":

!["Install the plugin from the plugin manager"](/assets/qgis_install_extension_en.png)

## Connect the plugin to Isogeo {#authentication}

When you launch the plugin for the very first time or clicking [on the button to change authentication in the settings tab](/usage/configuration.md)), the authentication form is displayed.

Just upload the credentials file `client_secrets.json`you must have received by email from Isogeo.

!["Load the credentials file client_secrets&#46;json received by email"](/assets/ui_auth_prompt_upload_credentials_file_en.png)

If you have an Isogeo account (means that you can [log in here](https://id.api.isogeo.com/)), you can check the  `I've got edition rights on app.isogeo.com` option.

_Et voilà !_ Enjoy!
