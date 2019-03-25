# Installation for development

**Developers** should use latest versions.

## Last packaged version

1. Download the [last plugin version released](https://github.com/isogeo/isogeo-plugin-qgis/releases) ;
2. Unzip it in `C:\Users\%USERNAME%\.qgis2\python\plugins` on Windows or `/home/$USER/.qgis2/python/plugins` on Ubuntu ;

## Development version

Clone the repository in  `C:\Users\%USERNAME%\.qgis2\python\plugins` on Windows or `/home/$USER/.qgis2/python/plugins` on Ubuntu, specifiying a foldername **without special character nor hyphen** (unlike the repository name...):

```bash
cd C:\Users\%USERNAME%\.qgis2\python\plugins
git clone https://github.com/isogeo/isogeo-plugin-qgis.git isogeo_search_engine_dev
```

It's also possible to clone the repository in any folder and add its path to the environment variable `QGIS_PLUGINPATH`.
