# Data formats automatically supported

In theory, the service can scan all formats supported by the FME ETL on which it is based. However, as new needs arise, new formats are added.

![Formats scanned automatically](/assets/Formats_WordCloud.png "Searching for data in Isogeo")

## File formats

* Esri shapefiles (.shp)
,* Esri Personal Geodatabase (.mdb),
* Esri File Geodatabase (.gdb),
* MapInfo tables (.tab),
* MapInfo Interchange Format (.mif / .mid),
* Intergraph GeoMedia database (.mdb),
* AutoCAD DWG (.dwg),
* AutoDesk DXF (.dxf),
* MicroStation DGN (.dgn),
* Google Earth - only the first layer is accepted (.kml / .kmz)
,* GPS eXchange Format (.gpx)
,* ER Mapper ECW (.ecw),
* GeoTIFF (.geotiff)
,* JPEG (.jpg / .jpeg),
* JPEG 2000 (.jp2),
* Portable Network Graphics (.png)
,* TIFF (.tiff),

## Database formats

* Esri Enterprise Geodatabase (ArcSDE)
,* Microsoft SQL Server Spatial (all versions),
* Oracle Spatial (all versions),
* PostGIS (all versions).

Because of their implementation, not all formats are supported to the same extent or in the same way. Table 1 also includes notes as to which licenses are required to support certain formats.

## Minimum licenses required

| Storage | Type    | Format                       | Required dependencies | FME license  |
|:-------- | ------- | ---------------------------- | -------------------------- | ------------ |
| Files | Vector   | MapInfo TAB                  | .tab, .dat, .id, . map      | Professional |
| Files | Vector   | Esri shapefile                 | .shp, .dbf, .shx           | Professional |
| Files | Vector   | MapInfo Interchange Format   | .mif, .mid                 | Professional |
| Files | Raster   | Enhanced Compression Wavelet | .ecw                       | Professional |
| Files | Raster   | GeoTIFF                      | .tiff / .tif / .geotiff    | Professional |
| Files | Raster   | JPEG 2000                    | .jp2 / .jpk                | Professional |
| Files | CAD       | AutoCAD DWG                  | .dwg, .prj                 | Professional |
| Files | CAD       | Autodesk Exchange Format     | .dxf, .prj                 | Professional |
| Files | CAD       | Microstation DGN             | .dgn                       | Professional |

