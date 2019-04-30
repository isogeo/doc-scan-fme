---
description: Parallélisation du Scan FME (Isogeo)
---

# Paralléliser le Scan {#scan_concurrency}

Le service de scan permet d&apos;utiliser jusqu&apos;à 5 instances de FME à partir de la même licence. Par défaut, l&apos;installation en utilise 3.

**Si** le serveur est suffisamment dimensionné pour supporter cette charge, il suffit d&apos;éditer le fichier *worker.bat* dans le dossier *daemon* de l&apos;installation du scan et de modifier le paramètre `MAX_FME_CONCURRENCY_LIMIT` puis de redémarrer le service.
