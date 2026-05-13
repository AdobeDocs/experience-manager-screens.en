---
title: Authoring with Data Triggers
description: Learn more about how to author with data triggers in an AEM Screens channel.
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: c95da2e9-a216-4d0a-85d0-a0fb895a8d8a
TQID: https://experienceleague.adobe.com/Iqb4pREvZNLalXSE6sNTZPV-uwqzBJKmztLuQtWfCW0
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
    internal-label: Experience Manager Screens
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a5fd0e22-1a77-4f49-a6af-7a57fff19aed
    internal-label: Authoring Screens
  - id: eb3ad9f8-54a2-45f3-abb1-d3976415a718
    internal-label: Personalization
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
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: ff2b9b37-92e0-45fc-b853-379d44c08c89
    internal-label: Audience segmentation
---
# Authoring with Data Triggers {#authoring-with-data-triggers}

This section highlights how to enable targeting in your channels.

>[!IMPORTANT]
>
>The minimum version that supports data triggers in an AEM Screens channel is AEM 6.5.3 Feature Pack 3.

## Prerequisites {#prereqs}

Before you follow the steps below to enable targeting in channels, learn the [Key Terms in Configuring in AEM Screens](configuring-context-hub.md) required for understanding ContextHub and Targeting in AEM Screens.

>[!IMPORTANT]
>
>It is recommended that you understand and set up ContextHub configurations, before enabling targeting in an AEM Screens channel.

Follow the links below for more information:

1. **[Setting up Data Store](configuring-context-hub.md)**
1. **[Setting up Audience Segmentation](configuring-context-hub.md)**

When you have completed the preceding steps, you are ready to enable targeting in your channels.

## Authoring with Data Triggers Overview {#author-targeting}

>[!VIDEO](https://video.tv.adobe.com/v/31921)

## Enabling Targeting in an AEM Screens Channel {#enabling-targeting}

Follow the steps below to enable targeting in your channels.

1. Navigate to one of the AEM Screens channels. The following steps demonstrate how to enable targeting by using **DataDrivenRetail** *(sequence channel)* created in an AEM Screens channel.

1. Click the channel **DataDrivenRetail** and click **Properties** from the action bar.

   ![screen_shot_2019-05-01at43332pm](assets/screen_shot_2019-05-01at43332pm.png)

1. Click the **Personalization** tab so you can set up the ContextHub configurations and click the ContextHub and Segments path.

    1. Click the **ContextHub Path** as **libs** > **settings** > **cloudsettings** > **default** > **ContextHub Configurations** and click **Click**.

    1. Click the **Segments Path** as **conf** > **`We.Retail`** > **settings** > **wcm** > **segments** and click **Click**.

    1. Click **Save & Close**.

   >[!NOTE]
   >
   >Use the ContextHub and the Segments path, where you initially saved your context hub configurations and segments.

   ![screen_shot_2019-05-01at44030pm](assets/screen_shot_2019-05-01at44030pm.png)

1. Navigate and click the **DataDrivenRetail** from **DataDrivenAssets** > **Channels** and click **Edit** from the action bar. Drag and drop the assets in your channel editor.

   >[!NOTE]
   >
   >If you have set up everything correctly, you see the **Targeting** option in the drop-down from the editor, as shown in the figure below.

   ![screen_shot_2019-05-01at44231pm](assets/screen_shot_2019-05-01at44231pm.png)

1. Click **Targeting**.

1. Click **Brand** and the **Activity** from the drop-down menu and click **Start Targeting**.

### Learn More: Example Use Cases {#learn-more-example-use-cases}

After you have configured ContextHub for your AEM Screens project, you can follow the different Use Cases to understand how data triggered assets plays a vital role in different industries:

1. **[Retail Inventory Targeted Activation](retail-inventory-activation.md)**
1. **[Travel Center Temperature Activation](local-temperature-activation.md)**
1. **[Hospitality Reservation Activation](hospitality-reservation-activation.md)**
