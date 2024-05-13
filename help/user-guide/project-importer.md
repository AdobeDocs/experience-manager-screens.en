---
title: New Project Importer from File
description: This functionality lets you bulk-import a set of locations from a CSV/XLS spreadsheet to your AEM Screens project.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: administering
docset: aem65
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 3bff9ef3-0d6f-41d8-a8ef-bcc5a795990e
---
# New Project Importer from File {#new-project-importer-from-file}

This section describes a functionality to bulk-import a set of locations from a CSV/XLS spreadsheet to your AEM Screens project.

## Introduction {#introduction}

When you are setting up an AEM Screens project for the first time in your organization, create all the locations too. If your project involves many locations, it results in a tedious task that involves much selecting and waiting in the UI.

The goal of this feature is to reduce the time required to set up the project and thus resolve budgeting issues.

By letting the author provide a spreadsheet as an input file, and letting the system automatically create the location tree in the back-end, this feature:

* *achieves way better performance than manually selecting through the UI*
* *lets the customer export the locations they have from their own system and easily import them directly in AEM*

This process saves both time and money during initial project setup or when extending the existing AEM Screens to new locations.

## Architectural Overview {#architectural-overview}

The following diagram showcases the architectural overview for Project Importer feature:

![screen_shot_2019-05-14at20618pm](assets/screen_shot_2019-05-14at20618pm.png)

### Data Model {#data-model}

The data model for Project Importer is described below:

>[!NOTE]
>
>The current release supports only importing locations.

| **Property** |**Description** |
|---|---|
| ***`path {string*}`*** |The resource path for the location |
| ***`[./jcr:title] {string*}`*** |The name of the template to use (that is, the location for *screens/core/templates/location*) |
| ***`template {string}`*** |Optional title to use for the page |
| ***`[./jcr:description] {string}`*** |Optional description to use for the page |

The spreadsheet (CSV/XLS) file thus requires the following columns:

* **path {string}** &ndash; The path for the location to be imported, where the root of the path is the location folder for the project (that is, *`/foo`* is imported to *`/content/screens/<project>/locations/foo`*)
* **template {string}** &ndash; The template to use for the new location, for now the only allowed value is "location", but this value is extended to all the Screens templates in the future (`display`, `sequencechannel`, and so on)
* **[./*] {string}** &ndash; Any optional property to be set on the location (that is, `./jcr:title`, `./jcr:description`, `./foo, ./bar`). The current release allows no filtering.

>[!NOTE]
>
>Any column that does not match the conditions above is ignored. For example, if you have any other column defined in your sheet (CSV/XLS) file other than **path**, **template**, **title**, and **description** in your file, those fields are ignored. And, **Project Importer** does not validate those additional fields for importing your project to your AEM Screens project.

## Using Project Importer {#using-project-importer}

The following section describes how the Project Importer is used in an AEM Screens project.

>[!CAUTION]
>
>Limitations:
>
>* Files other than CSV/XLS/XLSX extensions are not supported in the current release.
>* No filtering of the properties exists for imported files and anything starting with "./" is imported.
>

### Prerequisites {#prerequisites}

* Create a project titled as **DemoProjectImport**

* Use a sample CSV or Excel file that you must import.

For demo purposes, you can download an excel file from the section below.

[Get File](assets/minimal-file.xls)

### Importing the file with minimum required fields {#importing-the-file-with-minimum-required-fields}

Follow the steps below to import a file to a location folder with the minimum required fields:

>[!NOTE]
>
>The following example showcases the minimum four fields required to import your project:

![screen_shot_2019-05-14at21523pm](assets/screen_shot_2019-05-14at21523pm.png)

1. Navigate to your AEM Screens project (**DemoProjectImport**).

   ![screen_shot_2019-05-12at52651am](assets/screen_shot_2019-05-12at52651am.png)

1. Click the project,** DemoProjectImporter **>** Create **>** Import Locations** from the side bar.

   ![screen_shot_2019-05-12at52433am](assets/screen_shot_2019-05-12at52433am.png)

1. The **Import** wizard is displayed. Click the file for your project with locations or click the file (***minimal-file.xls***) you downloaded from the *Prerequisites* section.

   After you have selected the file, click **Next**.

   ![screen_shot_2019-05-15at113718am](assets/screen_shot_2019-05-15at113718am.png)

1. Verify the content of the file (locations) from the Import wizard and click **Import**.

   ![screen_shot_2019-05-12at53131am](assets/screen_shot_2019-05-12at53131am.png)

1. As a result, you can now view all the locations imported to your project.

   ![screen_shot_2019-05-12at53450am](assets/screen_shot_2019-05-12at53450am.png)
