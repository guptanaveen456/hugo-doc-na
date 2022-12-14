---
title: "Preparing database"
weight: 1
---

<!-- 1. [Modular MOM](c:\users\anil.birajdar\desktop\temp\index.html)
1. [Before You Start](c:\users\anil.birajdar\desktop\temp\Before-You-Start_127740192.html)
1. [Quick Start to Developing with Opcenter Modular Manufacturing](c:\users\anil.birajdar\desktop\temp\Quick-Start-to-Developing-with-Opcenter-Modular-Manufacturing_134455239.html)
1. [How to Create a Configurable Object](c:\users\anil.birajdar\desktop\temp\How-to-Create-a-Configurable-Object_125339498.html)
# **Modular MOM : Preparing a Database**  -->
Created by Unknown User (sergey.postoyalko), last modified by Alvarez Villanueva, Beatriz on Nov 08, 2021 

The following procedure explains how to prepare the database where a new Configurable Object will be created.
## **Procedure**
1. Open SQL Server Management Studio.
1. Make sure your login has the **sysadmin** role.
1. Do either of the following:
   1. To use any existing database, drop it by executing [the query for dropping existing database](#PreparingaDatabase-QueryforDroppingExistingDatabase).
   1. To create a new database, execute [the query for creation of a new database](#PreparingaDatabase-QueryforCreationofaNewDatabase).

**Query for Dropping Existing Database**

Before executing this query, replace **<database name>** with the name of the database you want to drop:

USE master

IF EXISTS(select \* from sys.databases where name='<database name>')

BEGIN

ALTER DATABASE <database name> SET SINGLE\_USER WITH ROLLBACK IMMEDIATE;

DROP DATABASE <database name>

END

CREATE DATABASE <database name>

ALTER DATABASE <database name> SET ALLOW\_SNAPSHOT\_ISOLATION ON

**Query for Creation of a New Database**

Before executing this query, replace **<database name>** with the name of your new database:

CREATE DATABASE <database name>

ALTER DATABASE <database name> SET ALLOW\_SNAPSHOT\_ISOLATION ON
## **Next Steps**
1. Create an empty folder for source code with a short name. For convenience the path to the created folder should contain no spaces.
1. Clone Git repositories into your folder for source code listed in the step 3 of [How to Create a Configurable Object](c:\users\anil.birajdar\desktop\temp\How-to-Create-a-Configurable-Object_125339498.html).
1. [Update NuGet.Config](c:\users\anil.birajdar\desktop\temp\Updating-NuGet.Config_127739663.html)

## **Attachments:**
![](Preparing-a-Database\_127739661.002.png) [Checking Login Properties.png](c:\users\anil.birajdar\desktop\temp\attachments\127739661\127739660.png) (image/png) 

Document generated by Confluence on Jul 28, 2022 11:21

[Atlassian](https://www.atlassian.com/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
