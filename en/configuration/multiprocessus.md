# Paralléliser le Scan {#scan_concurrency}

Le service de scan permet dutiliser jusquà 5 instances de FME à partir de la même licence. Par défaut, linstallation en utilise 3.

**Si** le serveur est suffisamment dimensionné pour supporter cette charge, il suffit déditer le fichier *worker.bat* dans le dossier *daemon* de linstallation du scan et de modifier le paramètre `MAX_FME_CONCURRENCY_LIMIT` puis de redémarrer le service.
