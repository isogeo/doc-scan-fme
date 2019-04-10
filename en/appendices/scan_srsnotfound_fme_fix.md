# Spatial Reference Systems (SRS) and unrecognized bounding boxes

There may be times when the scan does not enter the coordinate system or the convex envelope. Based on FME, you must ensure that projections are entered so that they can be read properly by the [ETL](https://en.wikipedia.org/wiki/Extract_transform_load).

## Case 1 (majority of cases): a bounding box, no SRS

In most cases, the problem stems from the fact that FME does not recognize the coordinate system. This does not mean that the system could not be read and used by FME. In short, FME uses the system definition, but does not recognize it.

![A bounding box, no SRS](/assets/annex_srsNotFound_case1_NoSRS_ButMap.png "Problem configuring FME projections - Case 1")

To fix this problem, you must "tell" FME how to recognize this system. There are two possible solutions:

### The system is a known system with an EPSG code

If you are looking to configure a single FME solution, go to the `Reproject/Exceptions` folder (in the FME installation directory), and edit the file corresponding to the format used. You must then find the paragraph for the country of the coordinate system. You must then add a new line for the system that you want to add, just like for the systems already present in this file.

![Modifying the esriwkt.db file](/assets/annex_srsNotFound_EditWKT.png "Adding a projection recognition to FME")

#### Examples

The Lambert93 coordinate system (EPSG 2154) for ESRI formats (Shapefile,
Geodatabases, etc.) is not recognized:

1. Open `esriwkt.db`,
2. Find the paragraph `French`,
3. By default, there are several definitions for the Lambert93 system;
4. Add your definition by copying it from the .prj file.

> Tip: if you do not have a `.prj` file (for example, if you store your data in geodatabase files), you can create one in the list of systems (right-click/Save as...).

The RGF93 / CC42 coordinate system (EPSG 3942) for the Oracle format is not
recognized:

1. Open document `oracle.db`,
2. Find the paragraph `French`,
3. Add the following line: `ORACLE|RGF93.CC42|3942`.

## Case 2: no bounding box, no SRS

If the record does not contain a bounding box, this infers that the reprojection could not be performed, which means that FME does not have the source system.

![No SRS, no bounding box](/assets/annex_srsNotFound_case2_NoSRS_NoMap.png "Problem configuring FME projections - Case 2")

This may occur for data formats that do not correctly manage the coordinate systems, as is the case with CAD files, for example.

### Resources

* find your coordinate system in the [EPSG official registry](http://epsg.io/);
* [French coordinate systems in FME](http://documentation.veremes.net/public/fme/fme_ft_systemes_de_projection_francais.pdf).
