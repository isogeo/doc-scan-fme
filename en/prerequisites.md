# Configuration

To be able to use the Isogeo Worker Service (Scan FME) on your workstation or server, you must define the following prerequisites:

## Operating system

We currently only support the following Windows systems:

* Windows 8 and 8.1 (recommended)
* Windows 7 (recommended)
* Windows Vista SP2
* Windows Server 2012 and 2012 R2 (recommended)
* Windows Server 2008 and 2008 R2
* Windows Server 2003 SP2
* Windows XP SP3 (except the 64-bit version)

Even if the Isogeo service can be installed on a user workstation, **we strongly advise using a server** in the interests performance, access and availability.

## Installing FME Desktop

FME Desktop must be installed and correctly configured on your workstation or server in order to access and manage your geographic data (editing choice, third-party components). For more details, please contact your FME distributor.

Isogeo service currently supports:

* FME Desktop 2013
* FME Desktop 2014
* FME Desktop 2015

and their service packs (SP1, SP2, SP3, SP4).

## User account

You must create a Windows user account that lets you:

* run FME Desktop on the machine on which the Isogeo service is installed,
* write in the Isogeo service installation directory,
* access network resources required to read your GIS data.

For example, you should create a new user account called Isogeo with the appropriate permissions.

## Security

If your server is connected to the Internet via a corporate network subject to security policies (which is usually the case), you must make sure that:

* your browser can access the various Internet sites managed by Isogeo (all our sites have domain names that end with isogeo.com, and all use HTTPS secure protocol), such as https://app.isogeo.com
* your operating system can connect to port **5671** of the **daemons-mq.isogeo.com** domain using **secure TCP protocol**.

You can usually obtain this information from an IT technician or your IT Services Manager.
