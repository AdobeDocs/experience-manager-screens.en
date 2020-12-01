---
title: Content Assignment Report
description: This page describes the downloading and usage of Content  Assignment Report.
---

# Content Assignment Report {#content-assignment-report}

The Content Assignment Report feature allows an AEM Screens administrator or an author to export a *Content Assignment Report* that could be in spreadsheet format.

## Using Content Assignment Report {#using-content-assignment-report}

The Content Assignment Report allows an AEM Screens author or an administrator to download the report that contains all the assets such as images, videos in in all Channels created in an AEM Screens project. Additionally, it includes the information of the entire channels assigned to all designated displays and henceforth all the devices assigned to their designated Displays.

### Using the Content Assignment Report Feature{#downloading-content-assignment-report-fp}

#### Setting up the Project {#setting-up-project}

Follow the steps below to download the Content Assignment Report from an AEM Screens project:

1. Create an AEM Screens titled as **DemoScreens**.

1. Create two sequence channels in **DemoScreens** such as **ChannelOne** and **ChannelTwo**.

1. Select **ChannelOne** and click **Edit** from the action bar. Add few assets (images/videos) to this channel. Similarly, add assets to **ChannelTwo**.

1. Navigate to the Locations folder from **DemoScreens** --> **Locations** and create three different locations titled as **SanJose**, **Dublin**, and **SanFrancisco**.

1. Navigate to each of the locations and create a display for each location such as **SanJoseMain** under **SanJose** location, **DublinMain** under **Dublin** location, and **SanFranciscoMain** under **SanFrancisco** location.

1. Assign a device to each of the display.

#### Downloading the Content Assignment Report {#downloading-content-assignment-report}

Once you have setup your AEM Screens project and have assigned displays to each of the locations as shown in the preceding steps.

>[!NOTE]
>The Content Assignment Report feature can only be accessed at the project level.

Follow the instructions below to download the Content Assignment Report:

1. Navigate to your AEM Screens project and select the project **DemoScreens**.

1. Click on Content Assignment Report from the action bar. An excel sheet should be downloaded to your local machine.

   >[!NOTE]
   >The downloaded excel sheet comprises of four columns such as **Channels**, **Assets**, **Displays**, and **Devices** which can used to further investigate all these four entities.




