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
|                                          Apic Exchange Format (.asc)                                              | x                      | x              | x                  |
| AutoCAD DWG (.dwg)                                                                                                | x                      | x              | x                  |
| AutoDesk DXF (.dxf)                                                                                               | x                      | x              | x                  |
| AutoDesk SDF (.sdf)                                                                                               | x                      | x              | x                  |
| ER Mapper ECW (.ecw)                                                                                              | x                      | x              | x                  |
| Esri ASCII Grid (.grd, .asc)                                                                                      | x                      | x              | x                  |
| Esri File Geodatabase (.gdb)                                                                                      | -                      | x              | x                  |
| Esri shapefiles (.shp)                                                                                            | x                      | x              | x                  |
| GeoJSON (.geojson)                                                                                                | x                      | x              | x                  |
| GeoTIFF (.geotiff)                                                                                                | x                      | x              | x                  |
| Google Earth (.kml / .kmz) [seulement la 1ère couche dans lordre alphabétique]                                    | x                      | x              | x                  |
| GPS eXchange Format (.gpx)                                                                                        | x                      | x              | x                  |
| JPEG (.jpg / .jpeg)                                                                                               | x                      | x              | x                  |
| JPEG 2000 (.jp2)                                                                                                  | x                      | x              | x                  |
| Lidar Data Exchange Format (.las, .laz, .lasd)                                                                    | x                      | x              | x                  |
| MapInfo tables (.tab)                                                                                             | x                      | x              | x                  |
| MapInfo Interchange Format (.mif / .mid)                                                                          | x                      | x              | x                  |
| MicroStation DGN (.dgn)                                                                                           | x                      | x              | x                  |
| Portable Network Graphics (.png)                                                                                  | x                      | x              | x                  |
| SpatiaLite (.sqlite)                                                                                              | x                      | x              | x                  |
| TIFF (.tiff)                                                                                                      | x                      | x              | x                  |
| XYZ (.xyz) [seulement pour les fichiers contenant 3 colonnes attributaires (X Y et Z) séparées par des espaces]   | x                      | x              | x                  |

## Les systèmes de gestion de bases de données (SGBD) {#sgbd}

La liste suivante présente les formats de SGBD pris en charge par le scan et l'édition de FME nécessaire pour pouvoir les scanner.

| SGBD                                   | Professional Edition   | Esri Edition   | Database Edition   |
|:--------------------------------------:|:----------------------:|:--------------:|:------------------:|
| Microsoft SQL Server Spatial           | x                      | x              | x                  |
| PostGIS                                | x                      | x              | x                  |
| Esri Enterprise Geodatabase (ArcSDE)   | -                      | x              | x                  |
| Oracle Spatial                         | -                      | -              | x                  |

Tous les formats ne sont néanmoins pas pris en compte au même degré et de la même façon, compte-tenu de leurs spécificités.
