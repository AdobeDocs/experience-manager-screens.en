---
title: Bulk Offline Update
description: Learn how you can update all the channels in bulk.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
noindex: true
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: d0a0b065-798e-4108-86ac-0a1f4e211cfc
TQID: https://experienceleague.adobe.com/PxlKWiWPvedqs2krdj3UH5Chshni2X3RaTmZI1wW2-Q
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
# Bulk Offline Update {#bulk-offline-update}

>[!IMPORTANT]
>This content is valid for AEM on-premise/AMS (AEM 6.5LTS and AEM 6.5). For AEM as a Cloud Service Screens content refer to the [AEM as a Cloud Service guide](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

This section covers the following topics on Bulk Offline Update:

* **Overview**
* **Using Bulk Offline Update**

<!--
OBSOLETE VERSIONS
>[!CAUTION]
>
>This AEM Screens functionality is only available, if you have installed AEM 6.3 Feature Pack 3 or AEM 6.4 Screens Feature Pack 1.
>
>To get access to this Feature Pack, contact Adobe Support and request access. When you have permissions you can download it from Package Share.
-->

## Overview {#overview}

Bulk Offline Update, lets you update all the channels in bulk. It avoids the hassle of navigating to a particular channel and update the content. Rather, you can update all the content in channels for one specific project in one instant.

You can also schedule this activity for a time of lower network traffic.

>[!NOTE]
>
>The Bulk Offline Update feature is optimized to update only those channels that have been modified.

## Using Bulk Offline Update {#using-bulk-offline-update}

You can manually use Bulk Offline Update from the User Interface (UI) or schedule the bulk update from OSGi services.

### Using AEM Screens User Interface {#using-aem-screens-user-interface}

Follow the steps below to use bulk offline update for an AEM Screens project:

1. Navigate to your AEM Screens project.
1. Click the project, then click **Update Offline Content** from the action bar so you can manually update the channel content.

   ![screen_shot_2018-04-24at122256pm](assets/screen_shot_2018-04-24at122256pm.png)

### Adobe Experience Manager Web Console Configuration {#adobe-experience-manager-web-console-configuration}

Follow the steps below to use bulk offline update for an AEM Screens project:

1. Adobe Experience Manager Web Console Configuration.
1. Search for Bulk Offline Update services.

   ![screen_shot_2018-04-24at121428pm](assets/screen_shot_2018-04-24at121428pm.png)

1. Add the following properties:

   **Project Path** - Specifies the path of your AEM Screens project. The path is usually `/content/screens/<Name of your project>`.

   *For example*, `/content/screens/we-retail`. You can find this path in the URL by selecting any project under AEM Screens (do not click the icon).

   >[!NOTE]
   >
   >Specify the project path relative to your channel.

   **Schedule Frequency** - Specifies a time, for example, 5:00 P.M. or 17:00 at which this service should update offline content.

1. Click **Save** to save your settings. Your content is updated at the specified time.
