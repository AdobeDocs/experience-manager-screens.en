---
title: Create and Manage Schedules
description: Learn about schedules that let you organize channels into reusable groups so that you do not have to repeat their assignment individually.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: dc9c5413-3b03-4f1f-bac5-aa599443254a
TQID: https://experienceleague.adobe.com/FJomd-Wz-r8vJZK7PH6wgL4LY3zRmOucBhIbTdjUmQ4
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
    internal-label: Experience Manager Screens
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a5fd0e22-1a77-4f49-a6af-7a57fff19aed
    internal-label: Authoring Screens
subfeature_v2:
  - id: ba4275ba-c29a-4197-90dc-5a633402ca3c
    internal-label: Channels
  - id: cf6d61d1-acb6-4411-ad1b-25fb57e94db6
    internal-label: Schedules
  - id: f5973e90-a5a3-4b84-8602-ee120d4ce9b1
    internal-label: Content
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
---
# Create and manage schedules {#creating-and-managing-schedules}

**Schedules** in AEM Screens let you organize channels into reusable groups. Doing so means that you do not have to repeat their assignment individually for each display on which you want to show your content.

Schedules, when combined with ***DayParting***, lets you set a global schedule with multiple channels running at specific times of the day, and reuse that set up for all your displays at once.

>[!NOTE]
>
>This AEM Screens functionality is only available if you have installed AEM 6.3 Sites Feature Pack 1. To get access to this Feature Pack, contact Adobe Support and request access. After you have the necessary permissions, you can download it from Package Share.

## Create a schedule {#creating-a-schedule}

You can create a schedule for your Screens project that can manage all the activities for your use case.

Follow the steps below to create a schedule for your channel:

1. Click the Adobe Experience Manager link (top left) and then Screens. Alternatively, you can go directly to: `http://localhost:4502/screens.html/content/screens`.
1. Navigate to Screens project and click **Schedules**.
1. Click **Create** from the action bar.
1. Click **Schedule** from the **Create** wizard and click **Next**.

1. Enter the **Name** and **Title** and click **Create**.

You can see a schedule folder with the designated name and title in your project.


## View dashboard {#viewing-dashboard}

After you have created a schedules folder in your project, you can view the details from the schedules dashboard.

Follow the steps below to view the schedule dashboard. The following example shows the dashboard of the `We.Retail` project:

1. Navigate to the **Schedules** folder of Screens (example, `We.Retail`) project.

   ![chlimage_1](assets/chlimage_1.png)

1. Click **Dashboard** from the action bar.

   You can view three different panels such as **SCHEDULE INFORMATION**, **ASSIGNED CHANNELS**, and **ASSIGNED DISPLAYS**.

   ![chlimage_1-1](assets/chlimage_1-1.png)

   **Schedule Information Panel** - Click Properties from the top-right corner from the SCHEDULE INFORMATION Panel to view/change properties of the schedule.

   **Assigned Channels Panel** - Click +Assign Channel from the top-right corner from the ASSIGNED CHANNELS Panel to open the Channel Assignment dialog box. 

   **Assigned Displays Panel** - Click any of the displays from the ASSIGNED DISPLAYS Panel to open the display dashboard.
