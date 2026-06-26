---
title: Creating and Managing Displays
description: Learn about creating a display and device configuration in AEM Screens. Also, learn about the display dashboard.
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: c55dc128-208d-4379-95a8-60a39d495dc0
TQID: https://experienceleague.adobe.com/orHLShhCxLB8T9Dm8Vvihvy7GNGrmJQZt8toCPs5c3k
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
    internal-label: Experience Manager Screens
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a5fd0e22-1a77-4f49-a6af-7a57fff19aed
    internal-label: Authoring Screens
subfeature_v2:
  - id: d8e42837-75d7-4e4e-accd-d0cdd8efe1f4
    internal-label: Displays
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
# Creating and Managing Displays {#creating-and-managing-displays}

>[!IMPORTANT]
>This content is valid for AEM on-premise/AMS (AEM 6.5LTS and AEM 6.5). For AEM as a Cloud Service Screens content refer to the [AEM as a Cloud Service guide](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

A display is a virtual grouping of screens that are positioned next to each other. The display is permanent in respect to an installation. It is the object content authors work with and always reference to as logical display rather than their physical counter parts.

When you create a location, you have to create a display for your location.

This page shows creating and managing displays for Screens.

**Pre-requisites**:

* [Configuring and Deploying Screens](configuring-screens-introduction.md)
* [Create and Manage Screens Project](creating-a-screens-project.md)
* [Create and Manage Channels](managing-channels.md)
* [Create and Manage Locations](managing-locations.md)

## Creating a New Display {#creating-a-new-display}

>[!NOTE]
>
>Create a location before creating a display. See [Create and Manage Locations](managing-locations.md) for more information.

1. Navigate to the appropriate location, for example `http://localhost:4502/screens.html/content/screens/TestProject`.
1. Click your location folder and click **Create** that is next to the plus icon in the action bar. 
1. Click **Display** from the **Create** wizard, then click **Next**.
1. Enter your **Name** and **Title** for your display location.
1. Under the **Display** tab, choose the details of the Layout. Choose the desired **Resolution**, such as **Full HD**. Choose the number of devices horizontally and vertically.
1. Click **Create**.

The display (*StoreDisplay*) is created and added to the location (*SanJose*).

![display](assets/display.gif)

When you have a display in position, the next step is to create a device config for that particular display.

>[!NOTE]
>
>**The Next Step**:
>
>When you create a display for your location, assign a channel to your display to use the content.
>
>See the [Assign Channels](channel-assignment.md) section to learn how to assign a channel to the display.

## Creating a New Device Config {#creating-a-new-device-config}

A device config acts as a placeholder for an actual digital signage device that is not yet installed.

1. Navigate to the appropriate display, for example, `http://localhost:4502/screens.html/content/screens/TestProject/locations/newlocation`.
1. Click your display folder and click **View Dashboard** in the action bar.
1. Click **+ Add Device Config** on the top-right of the **Devices** panel.

1. Click the **Device Config** as the required template and click **Next**.

1. Enter the properties as required and click **Create**.

The device config is created and added to the current display (in the following demonstration, the new device config is *DeviceConfig*).

![deviceconfig](assets/deviceconfig.gif)

>[!NOTE]
>
>When a device config is set to your display in the location, the next step will be to assign a channel to your display.
>
>As shown in the figure below, if the device config is displayed as unassigned in the **DEVICES** panel, if no channel is assigned to that particular device config.
>
>You should have a prior understanding of creating and managing channels. See [Create and Manage Channels](managing-channels.md) for more details.

![chlimage_1-9](assets/chlimage_1-9.png)

## Display Dashboard {#display-dashboard}

The display dashboard provides you with different panels for managing display devices. It also lets you configure your device.

![screen_shot_2018-08-23at42810pm](assets/screen_shot_2018-08-23at42810pm.png)

>[!NOTE]
>
>You can click the dashboard lists and trigger bulk actions on items, instead of going through each item individually.
>
>For example, the following image shows how you can click multiple channels from the display dashboard.

![cqdoc9456](assets/cqdoc9456.gif)

### Display Information Panel {#display-information-panel}

The **DISPLAY INFORMATION** Panel provides the display properties.

Click (**...**) in the top-right corner in the **DISPLAY INFORMATION** panel so you can view the properties and preview the display.


#### Viewing Properties {#viewing-properties}

Click **Properties** so you can view or change the properties of your display.

Also, you can adjust the event timer value for your interactive channel under the **Display** tab. The default value is set to *300 seconds*.

Use **CRXDE Lite**, to access the **idleTimeout** property, that is, `http://localhost:4502/crx/de/index.jsp#/content/screens/we-retail/locations/demo/flagship/single/jcr%3Acontent/channels`.


### Assigned Channels Panel {#assigned-channels-panel}

The **ASSIGNED CHANNELS** panel displays the assigned channels to this device.


### Devices Panel {#devices-panel}

The **DEVICES** Panel provides information on the device configurations.

Click (**...**) in the top-right corner in the **DEVICES** panel so you can add device configurations and update devices.

Also, click the device config to view properties, assign a device, or delete it completely.

![chlimage_1-13](assets/chlimage_1-13.png)

#### The Next Steps {#the-next-steps}

When you complete creating a display for your location, assign a channel for your display.

See [Assign Channels](channel-assignment.md) for more details.

