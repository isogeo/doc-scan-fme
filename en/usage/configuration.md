# Configuration and settings

## Authentication

### Request and set API credentials

Isogeo is a secured SaaS platform, so applications which use its data have to be authenticated (oAuth2 protocol). API credentials are a key pair, with an _id_ and a _secret_. A graphic form allows the user to set it. Credentials are stored in [the QGIS authentication base](http://docs.qgis.org/2.18/en/docs/user_manual/auth_system/auth_overview.html#authentication-database) if user enabled it before or in Qsettings if not.

The [authentication form](/installation/standard.md#auth-form) shows up when:

* the plugin is launched for the first time,
* the API credentials have expired.

![](/assets/ui_auth_prompt_en.png "Authentication form to enter API keys")

### Change API credentials

In the `Settings` tab, it's possible to change API keys:

![](/assets/settings_switch_api_en.png "Change API authentication")

---

## Share catalogs to the plugin


Create a share to the application *QGIS Plugin* in the administration console on [APP](https://app.isogeo.com/admin/shares);

![](/assets/app_share_toPlugin_en.png "A share to publish metadata into the plugin from Isogeo administration console")

---

## Display shares which are feeding the plugin

In the `Settings` tabs, informations about the application are displayed:

![](/assets/settings_shares_details_en.png "Informations about application in the Settings tab")

* name of the application declared to the Isogeo platform, corresponding to the plugin in use,
* count of shares feeding the plugin in use. Then, each share is described:
  * the share name - a clic opens the administration console on Isogeo,
  * the share last update,
  * the Isogeo workgroup owning the share and its email contact
