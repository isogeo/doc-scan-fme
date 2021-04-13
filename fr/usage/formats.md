---
description: Formats (shp, tab, ecw, tiff...) pris en compte par le Scan FME (Isogeo)
---

# Les formats de données pris en charge automatiquement 

Le service est théoriquement capable de scanner l’ensemble des formats pris en compte par l’ETL FME sur lequel il est basé. Cependant, nous ajoutons les nouveaux formats au fur et à mesure des besoins rencontrés.

![Les formats scannés automatiquement](/assets/Formats_WordCloud.png "Chercher les données dans Isogeo")

## Les formats de fichiers {#formats_files}

La liste suivante présente les formats de données pris en charge par le scan et l'édition de FME nécessaire pour pouvoir les scanner.

| Formats de fichiers                                                                                               | Professional Edition   | Esri Edition   | Database Edition   |
|:-----------------------------------------------------------------------------------------------------------------:|:----------------------:|:--------------:|:------------------:|
|                                          Apic Exchange Format (.asc)                                              | x                      | -              | -                  |
| AutoCAD DWG (.dwg)                                                                                                | x                      | -              | -                  |
| AutoDesk DXF (.dxf)                                                                                               | x                      | -              | -                  |
| AutoDesk SDF (.sdf)                                                                                               | x                      | -              | -                  |
| ER Mapper ECW (.ecw)                                                                                              | x                      | -              | -                  |
| Esri ASCII Grid (.grd, .asc)                                                                                      | x                      | -              | -                  |
| Esri File Geodatabase (.gdb)                                                                                      | x                      | -              | -                  |
| Esri Personal Geodatabase (.mdb)                                                                                  | x                      | -              | -                  |
| Esri shapefiles (.shp)                                                                                            | x                      | -              | -                  |
| Geography Markup Language (.gml) [seulement la 1ère couche dans lordre alphabétique]                              | x                      | -              | -                  |
| GeoTIFF (.geotiff)                                                                                                | x                      | -              | -                  |
| Google Earth (.kml / .kmz) [seulement la 1ère couche dans lordre alphabétique]                                    | x                      | -              | -                  |
| GPS eXchange Format (.gpx)                                                                                        | x                      | -              | -                  |
| Intergraph GeoMedia database (.mdb)                                                                               | x                      | -              | -                  |
| JPEG (.jpg / .jpeg)                                                                                               | x                      | -              | -                  |
| JPEG 2000 (.jp2)                                                                                                  | x                      | -              | -                  |
| Lidar Data Exchange Format (.las, .laz, .lasd)                                                                    | x                      | -              | -                  |
| MapInfo tables (.tab)                                                                                             | x                      | -              | -                  |
| MapInfo Interchange Format (.mif / .mid)                                                                          | x                      | -              | -                  |
| MicroStation DGN (.dgn)                                                                                           | x                      | -              | -                  |
| Portable Network Graphics (.png)                                                                                  | x                      | -              | -                  |
| SpatiaLite (.sqlite)                                                                                              | x                      | -              | -                  |
| TIFF (.tiff)                                                                                                      | x                      | -              | -                  |
| XYZ (.xyz) [seulement pour les fichiers contenant 3 colonnes attributaires (X Y et Z) séparées par des espaces]   | x                      | -              | -                  |

## Les systèmes de gestion de bases de données (SGBD) {#sgbd}

La liste suivante présente les formats de SGBD pris en charge par le scan et l'édition de FME nécessaire pour pouvoir les scanner.

| SGBD                                   | Professional Edition   | Esri Edition   | Database Edition   |
|:--------------------------------------:|:----------------------:|:--------------:|:------------------:|
| Esri Enterprise Geodatabase (ArcSDE)   | -                      | x              | -                  |
| Microsoft SQL Server Spatial           | x                      | -              | -                  |
| Oracle Spatial                         | -                      | -              | x                  |
| PostGIS                                | x                      | -              | -                  |

Tous les formats ne sont néanmoins pas pris en compte au même degré et de la même façon, compte-tenu de leurs spécificités.
