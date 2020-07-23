# Isogeo Worker service releases (Scan FME)

This platform-independent service is upgraded to correct any bugs, or to add new features (such as new formats). Note: these upgrades are not the same as upgrades to the scans administration interface, accessed via https://app.isogeo.com/admin/isogeo-worker.

To check which version of the service is installed on your machine, hover the mouse over the indicator light(s) at the top right of the scan administration interface:

![FME scan - version](/assets/service_version.png "Checking the service version")

### 1.3.4

* Add LAS format
* (Fix) a scan continue even if the service couldnt access a system folder

### 1.3.3

* (Fix) The convex hull are generated even if coordinates system isnt recognized (value *_FME_0*)

### 1.3.2

* New [NSSM](http://nssm.cc/) version (used to manage the Windows service)
* (Fix) Service uninstall on a 32-bit machine

### 1.3.1

* (Fix) Ability to read the ArcSDE format on Oracle.

### 1.3.0

* (Fix) Retrieves layers with no attributes shown;
* Improved support for KML/KMZ format;
* Improved support for GPx format;
* Deleting the SQL query scan for Créteil;
* Scanning of tables that have no geometry for Créteil.

### 1.2.0

* Apic ASC Format

### 1.1.1

* GPx format;
* PNG format.

### 1.1.0

* SQL query scan for Créteil / Plaine Centrale.

### 1.0.24

* KML/KMZ format.

### 1.0.23

* Deleting tables shown in duplicate by FME.

### 1.0.21

* Possibility of stopping a query.

_________

> Services below this line are considered obsolete, and the indicator light is orange.

![Scan FME - obsolete version](/assets/service_version_obsolete.png "Obsolete service")

### 1.0.20

* ESRI Grid format (.asc);
* JPEG format (.jpg and .jpeg).

### 1.0.19

* Improved calculation time for signature via FME (data marked as modified the first time);
* Retrieves FME errors to improve support.

### 1.0.18

* Support for FME SDE30 reader, used to read ArcSDE databases with a Professional license;
* Retrieves more information from CAD data (only the information for one layer was shown previously).

### 1.0.17

* Addition of correct 32-bit and 64-bit NSSM versions.

### 1.0.16

* Most recent NSSM version.
