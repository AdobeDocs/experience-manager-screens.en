---
title: Managing Devices
description: Learn about device assignment and management in AEM Screens.
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 10749ff2-9128-44e7-9f10-c8e783a6f695
---
# Managing Devices {#managing-devices}

This page describes device assignment.

The Devices console lets you access the device manager to assign your device to a display.

>[!CAUTION]
>
>Before assigning your device, register it. See [Device Registration](device-registration.md).

## Device Assignment {#device-assignment}

Follow the steps below to assign a device to a display:

1. Navigate to the Devices folder of your project, for example

   `http://localhost:4502/screens.html/content/screens/TestProject`

   ![chlimage_1-32](assets/chlimage_1-32.png)

1. Select your **Devices** folder and select **Device Manager** in the action bar. The assigned and unassigned devices display.

   ![chlimage_1-33](assets/chlimage_1-33.png)

1. Select an unassigned device from the list, and select the **Assign Device** in the action bar.

   ![chlimage_1-34](assets/chlimage_1-34.png)

1. Select the display that you want to assign the device to from the list, and select the **Assign**.

   ![chlimage_1-35](assets/chlimage_1-35.png)

1. Select the **Finish** to complete the assignment process.


   The display dashboard displays the assigned device in the **DEVICES** panel.

   ![chlimage_1-37](assets/chlimage_1-37.png)

   Select the (**...**) on the top-right corner of the **DEVICES** panel to either add device config or update the devices.

   ![chlimage_1-38](assets/chlimage_1-38.png)

>[!NOTE]
>
>Every time the first device is added to a new Screens project, a user group is created.
>For instance, if the project node name is *we-retail*, then the user group name is *screens-we-retail-devices*.
>This group is added as a member of the **Contributors** group, as shown in the figure below:

![chlimage_1-39](assets/chlimage_1-39.png)

### The Next Steps {#the-next-steps}

After you are familiar with assigning channel to a display, see t[Monitor and troubleshoot](monitoring-screens.md).
