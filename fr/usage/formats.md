---
description: Formats (shp, tab, ecw, tiff...) pris en compte par le Scan FME (Isogeo)
---

# Les formats de données pris en charge automatiquement 

Le service est théoriquement capable de scanner l’ensemble des formats pris en compte par l’ETL FME sur lequel il est basé. Cependant, nous ajoutons les nouveaux formats au fur et à mesure des besoins rencontrés.

![Les formats scannés automatiquement](/assets/Formats_WordCloud.png "Chercher les données dans Isogeo")

## Les formats de fichiers {#formats_files}

La liste suivante présente les formats de données pris en charge par le scan : 

| Formats de fichiers                                                                                               |
|:-----------------------------------------------------------------------------------------------------------------:|
|                                          Apic Exchange Format (.asc)                                              |
| AutoCAD DWG (.dwg)                                                                                                |
| AutoDesk DXF (.dxf)                                                                                               |
| AutoDesk SDF (.sdf)                                                                                               |
| ER Mapper ECW (.ecw)                                                                                              |
| Esri ASCII Grid (.grd, .asc)                                                                                      |
| Esri File Geodatabase (.gdb)                                                                                      |
| Esri shapefiles (.shp)                                                                                            |
| GeoJSON (.geojson)                                                                                                |
| GeoTIFF (.geotiff)                                                                                                |
| Google Earth (.kml / .kmz) [seulement la 1ère couche dans lordre alphabétique]                                    |
| GPS eXchange Format (.gpx)                                                                                        |
| JPEG (.jpg / .jpeg)                                                                                               |
| JPEG 2000 (.jp2)                                                                                                  |
| Lidar Data Exchange Format (.las, .laz, .lasd)                                                                    |
| MapInfo tables (.tab)                                                                                             |
| MapInfo Interchange Format (.mif / .mid)                                                                          |
| MicroStation DGN (.dgn)                                                                                           |
| Portable Network Graphics (.png)                                                                                  |
| SpatiaLite (.sqlite)                                                                                              |
| TIFF (.tiff)                                                                                                      |
| XYZ (.xyz) [seulement pour les fichiers contenant 3 colonnes attributaires (X Y et Z) séparées par des espaces]   |

## Les systèmes de gestion de bases de données (SGBD) {#sgbd}

La liste suivante présente les formats de SGBD pris en charge par le scan : 

| SGBD                                   |
|:--------------------------------------:|
| Microsoft SQL Server Spatial           |
| PostGIS                                |
| Esri Enterprise Geodatabase (ArcSDE)   |
| Oracle Spatial                         |

Pour les SGBD, le Scan a la particularité de remonter également les tables sans géométries et de créer des fiches de données tabulaires non géographiques.

Tous les formats ne sont néanmoins pas pris en compte au même degré et de la même façon, compte-tenu de leurs spécificités.