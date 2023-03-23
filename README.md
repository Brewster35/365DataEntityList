# 365DataEntityList

> **Overview**

This software generates a handy list of 365 Finance and Operations data entity metadata which can be used to identify which data entity is most appropriate for a specific scenario.

It works by populating a table with the metadata in a batch job which can then be downloaded as an Excel file.

> **Installation**

Create a new folder called "models" on the C drive and copy the model file into it.

Open a command prompt and run the following command:

    "K:\AosService\PackagesLocalDirectory\Bin\ModelUtil.exe" -import -metadatastorepath="K:\AosService\PackagesLocalDirectory" -file="C:\models\Brewsterware-Brewsterware.axmodel"

Rebuild the Brewsterware model in Visual Studio.

> **Preparation for use**

System Administration -> Setup -> Client performance options

Under the server scalability section, change the "maximum number of rows to export to Excel" to 70,000

> **Rebuilding the data**

After the Brewsterware model has been installed and built, a new tile will be visible in the data management workspace.

![Data management workspace](https://github.com/Brewster35/365DataEntityList/blob/main/images/workspace.png)

Clicking on the new tile will reveal a new form. The grid in this form will initially be empty. Click on the "Refresh entity list" menu item on the toolbar and confirm that you want to refresh the data in the form. 

![Data management workspace](https://github.com/Brewster35/365DataEntityList/blob/main/images/newform.png)

Specify a language from the dropdown on the batch form and click on ok to start the batch process.

![Data management workspace](https://github.com/Brewster35/365DataEntityList/blob/main/images/batch.png)

When the batch process has finished, the contents of the grid can be downloaded.

![Data management workspace](https://github.com/Brewster35/365DataEntityList/blob/main/images/export.png)

|Field name|Description|
| ----------- | ----------- |
|AOT Name|This is the name of the data entity as shown in the AOT. It is also the name of the view that is created in SQL server.|
|Entity name|This is the name of the data entity as shown in the data management workspace.|
|Modules|Shows the module that the data entity is related to.|
|Configuration key|If a configuration key is needed to enable the entity, this will show the path.|
|Country/region applicability|Countries the data entitiy is enabled for.|
|Data management enabled|This shows whether the entity is enabled for use with data management.|
|Multithreading enabled|This shows whether it is possible to use multithreading with the entity as setup in entity execution import parameters. This can be found on the entity settings tab of the Data import/export framework parameters.|
|Supports set based operations|This shows whether the entity is capable of adding the records to the target table in a single operation rather than row by row.|
|ODATA enabled|This shows whether the entity can be accessed using ODATA.|
|Is config related|If this is set to "Yes", then the entity is used for "parameter" based tables.|
|Staging table|This is the name of the staging table which is used with data management.|
|Read only|This shows whether the data entity is read only.|
|Entity collection name|This shows the name of the data entity when accessed using ODATA.|
|Entity field|This is the name of the field that is exposed on the data entity.|
|Entity field label|This is the label used for the field on the data entity.|
|Is mandatory|This shows whether the field is mandatory when creating a new record.|
|Datasource name|This is the unique name of the data source in the data entity. A lot of the time this is the same name as the underlying table.|
|Table name|This is the name of the table for the data source.|
|Table label|This is a more descriptive name for the table.|
|Field name|This is the name of the field on the table which is mapped to the entity field.|
|Field label|This is a more descriptive name for the field.|
|Is computed field|This shows whether the data for the entity field is generated using business logic instead of being mapped directly to a field on a table.|
|Data access modifier|This shows whether the entity field is accessible through ODATA or data management. Values can be public, private or Internal.|
|Is field in primary key|This shows whether the field forms part of the primary key for the entity.|
|String length|This shows the number characters that can be stored in the field if the field is of type String.|
|Data type|This is the type of data that is stored in the field.|
