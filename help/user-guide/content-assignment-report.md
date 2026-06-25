---
title: Content Assignment Report
description: Learn the downloading and usage of Content Assignment Report as it relates to AEM Screens.
feature: Authoring Screens
role: Developer
level: Intermediate
exl-id: 7397aa99-97fc-45c2-a157-c1bd7b1700b5
TQID: https://experienceleague.adobe.com/Pwq3ebRrbCufXFMk7R-FJj90xq4b7gLOcLvslch2L5o
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
    internal-label: Experience Manager Screens
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a5fd0e22-1a77-4f49-a6af-7a57fff19aed
    internal-label: Authoring Screens
subfeature_v2:
  - id: f5973e90-a5a3-4b84-8602-ee120d4ce9b1
    internal-label: Content
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
---
# Content Assignment Report {#content-assignment-report}

>[!IMPORTANT]
>This content is valid for AEM on-premise/AMS (AEM 6.5LTS and AEM 6.5). For AEM as a Cloud Service Screens content refer to the [AEM as a Cloud Service guide](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

The Content Assignment Report feature allows an AEM Screens administrator or an author to export a *Content Assignment Report* in a spreadsheet format.

## Using Content Assignment Report {#using-content-assignment-report}

The Content Assignment Report allows an AEM Screens author or an administrator to download the report that contains all the assets such as images, videos in all Channels created in an AEM Screens project. Also, it includes the information of the entire channels assigned to all designated displays and henceforth all the devices assigned to their designated Displays.

The Content Assignment Report not only allows a preview of all the Channels, Assets, Displays, and Devices in the selected AEM Screens project but also provides a high-level structure of your project.


### Pre-requisites {#pre-reqs}

Before downloading the Content Assignment Report, make sure you have set up an AEM Screens project with Channels, Locations, and Devices.
See the following resources for more details:

1. [Creating and Managing Projects](/help/user-guide/creating-a-screens-project.md)
1. [Creating and Managing Channels](/help/user-guide/managing-channels.md)
1. [Creating and Managing Locations](/help/user-guide/managing-locations.md)
1. [Creating and Managing Displays](/help/user-guide/managing-displays.md)
1. [Creating Devices](/help/user-guide/managing-devices.md)
1. [Assigning Channels](/help/user-guide/channel-assignment-latest-fp.md)


## Downloading the Content Assignment Report {#downloading-content-assignment-report-fp}

When you have setup your AEM Screens project and have assigned displays to each of the locations as shown in the preceding steps, download the Content Assignment Report.

>[!NOTE]
>The Content Assignment Report feature can only be accessed at the project level.

Follow the instructions below to download the Content Assignment Report:

1. Navigate to your AEM Screens project and click the project **DemoScreens**.

1. Click **Content Assignment Report** from the action bar.

   ![image](/help/user-guide/assets/content-assignment-report/can-download.png)

1. The downloaded spreadsheet consists of two tabs, such as **Locations** and **Content**. The Location tab displays four columns such as **Locations**, **Displays**, **Channels**, and **Devices** that can be used for investigating these four entities pertaining to your AEM Screens project.

   ![image](/help/user-guide/assets/content-assignment-report/report-sheet1.png)

   >[!NOTE]
   >The data displayed in the spreadsheet is alphabetically sorted in an easy-to-read format.

1. Selecting any of the channels from the **Channels** column opens the **Content** tab. In turn, it directly navigates you to that channel and gives you information on assets (images and videos) associated with that specific channel.

   ![image](/help/user-guide/assets/content-assignment-report/report-sheet2.png)
