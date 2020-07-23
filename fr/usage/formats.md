---
description: Formats (shp, tab, ecw, tiff...) pris en compte par le Scan FME (Isogeo)
---

# Les formats de données pris en charge automatiquement 

Le service est théoriquement capable de scanner l’ensemble des formats pris en compte par l’ETL FME sur lequel il est basé. Cependant, nous ajoutons les nouveaux formats au fur et à mesure des besoins rencontrés.

![Les formats scannés automatiquement](/assets/Formats_WordCloud.png "Chercher les données dans Isogeo")

## Les formats de fichiers {#formats_files}

* Apic Exchange Format (.asc),
* AutoCAD DWG (.dwg),
* AutoDesk DXF (.dxf),
* AutoDesk SDF (.sdf),
* ER Mapper ECW (.ecw),
* Esri ASCII Grid (.grd, .asc),
* Esri File Geodatabase (.gdb),
* Esri Personal Geodatabase (.mdb),
* Esri shapefiles (.shp),
* Geography Markup Language (.gml) [*seulement la 1ère couche dans lordre alphabétique*],
* GeoTIFF (.geotiff),
* Google Earth (.kml / .kmz) [*seulement la 1ère couche dans lordre alphabétique*],
* GPS eXchange Format (.gpx),
* Intergraph GeoMedia database (.mdb),
* JPEG (.jpg / .jpeg),
* JPEG 2000 (.jp2),
* Lidar Data Exchange Format (.las, .laz, .lasd),
* MapInfo tables (.tab),
* MapInfo Interchange Format (.mif / .mid),
* MicroStation DGN (.dgn),
* Portable Network Graphics (.png),
* SpatiaLite (.sqlite),
* TIFF (.tiff),
* XYZ (.xyz) [*seulement pour les fichiers contenant 3 colonnes attributaires (X Y et Z) séparées par des espaces*].

## Les systèmes de gestion de bases de données (SGBD) {#sgbd}

* Esri Enterprise Geodatabase (ArcSDE) [*licence FME Esri Edition nécessaire*]
* Microsoft SQL Server Spatial (toutes versions) ;
* Oracle Spatial (toutes versions),
* PostGIS (toutes versions),

Tous les formats ne sont néanmoins pas pris en compte au même degré et de la même façon, compte-tenu de leurs spécificités.
