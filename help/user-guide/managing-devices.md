---
title: Manage Devices
description: Learn about device assignment and management in AEM Screens.
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 10749ff2-9128-44e7-9f10-c8e783a6f695
TQID: https://experienceleague.adobe.com/BtVUYTZ9GisSxK6-M-QsYRGdykFB51IchqI7CX-vsa8
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
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
---
# Manage devices {#managing-devices}

This page describes the device assignment.

The Devices console lets you access the device manager to assign your device to a display.

>[!CAUTION]
>
>Before assigning your device, register it. See [Device Registration](device-registration.md).

## Device Assignment {#device-assignment}

Follow the steps below to assign a device to a display:

1. Navigate to the Devices folder of your project, for example

   `http://localhost:4502/screens.html/content/screens/TestProject`

   ![chlimage_1-32](assets/chlimage_1-32.png)

1. Click your **Devices** folder and click **Device Manager** in the action bar. The assigned and unassigned devices display.

   ![chlimage_1-33](assets/chlimage_1-33.png)

1. Click an unassigned device from the list, then in the action bar, click **Assign Device**.

   ![chlimage_1-34](assets/chlimage_1-34.png)

1. Click the display that you want to assign the device to from the list, and click the **Assign**.

   ![chlimage_1-35](assets/chlimage_1-35.png)

1. Click the **Finish** to complete the assignment process.


   The display dashboard displays the assigned device in the **DEVICES** panel.

   ![chlimage_1-37](assets/chlimage_1-37.png)

   Click the (**...**) on the top-right corner of the **DEVICES** panel to either add device config or update the devices.

   ![chlimage_1-38](assets/chlimage_1-38.png)

>[!NOTE]
>
>Every time the first device is added to a new Screens project, a user group is created.
>For instance, if the project node name is *we-retail*, then the user group name is *screens-we-retail-devices*.
>This group is added as a member of the **Contributors** group, as shown in the figure below:

![chlimage_1-39](assets/chlimage_1-39.png)

### The Next Steps {#the-next-steps}

After you are familiar with assigning channel to a display, see t[Monitor and troubleshoot](monitoring-screens.md).
