# Adding a new database to scan

## Overall approach

Proceed as follows to create a "Database" entry point:

1. In the "Scan FME" menu, click on "+ New" to create a new entry point.
2. Select the "Database" type.
3. Name the entry point. For example: Reference database.
4. Select the database type from the drop-down list.
5. Enter the connection settings.
6. Save.

    ![New database entry point](/assets/new_DB_ready.png "The new entry point is ready to be scanned")

## Settings required depending on the database type

Key:

* X = required
* \ = optional
* \- = disabled

| Field                           | PostGIS | Oracle | SQL Server | + Esri (SDE) |
| --------------------------- | :-----: | :----: | :--------: | :----------------------: |
| Name                         | X       | X      | X          | X                        |
| Type                           | X       | X      | X          | X                        |
| Server                        | X       | X      | X          |                         |
| Port                            | X       |        |            |                          |
| Identifier                  | X       | X      | X          |                          |
| Password                 | X       | X      | X          |                          |
| Database name      | X       |        | X          |                          |
| Connection file (.sde) | -       |        |            | X                        |
| Instance name            | -       |        |            | X                        |
| Transactional version   | -       |        |            | X                        |
