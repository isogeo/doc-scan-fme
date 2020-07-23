# How the FME scan works

## Process

1.	Click on the "Scan" button opposite the selected entry point. The list of queries is displayed.

    ![Entry point requests](/assets/EntryPoint_Requests.png "Displaying the history of requests made on an entry point")

2.	Click on the line of a request in progress to view the scan.

    ![Scan procedure](/assets/ProcessLive_GeoFLA_2014-12-26.gif "The scan process in action")

3.	The scan operation comprises 3 phases:
    4.	Inventorize: the scan establishes the list of data;
    5.	Sign: the scan signs all the data it has inventorized to mark the data when scanned, and to be able to deduce whether the data has already been scanned previously or modified since the last scan;
    6.	Document: the scan creates the records for newly detected data, or updates the records for modified data.

    ![Formats scanned automatically](/assets/PostGIS_requete_annot.png "Data search in Isogeo")

4.	Once it has finished, the scan indicates:
	* The complete list of data inventorized. Each data item in this list is characterized by a unique identifier, its name, location, format and status (new, modified, unchanged, deleted, error). You can sort this list;
	* List of data without geographic entities;
	* List of duplicate data;

The list of data without geographic entities and the list of duplicate data are given by way of information. They allow you to take the appropriate measures within your database.

The complete list of data inventorized by the scan allows you to identify the following:
* New data added to your inventory
* Data that has not changed since the last scan
* Data that has been modified since the last scan
* Data that has been deleted since the last scan

Go to the inventory to discover this data and browse the corresponding metadata.

## Special cases

- If you copy a data item without changing the file name, the scan will indicate that it has detected a duplicate, but will still create a new record.
- It is not possible to rename an entry point at present; you must delete it and re-create another.
- A table that is visible from several entry points (different data connections) will not be duplicated.
