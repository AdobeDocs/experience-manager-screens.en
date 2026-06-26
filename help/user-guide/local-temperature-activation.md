---
title: Travel Center Temperature Activation
description: Using AEM Screens, learn how this use case demonstrates the usage of travel center local temperature activation based on the values populated in Google Sheets.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 2ec2891f-0fbe-4812-b3c4-ff160ead36b8
TQID: https://experienceleague.adobe.com/C8FAKzAKUjdochkR96MShKiu2Ig-g-9BDnoX09g4xnM
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
# Travel Center Temperature Activation {#travel-center-temperature-activation}

>[!IMPORTANT]
>This content is valid for AEM on-premise/AMS (AEM 6.5LTS and AEM 6.5). For AEM as a Cloud Service Screens content refer to the [AEM as a Cloud Service guide](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

The following use case demonstrates the usage of travel center local temperature activation based on the values populated in Google Sheets.

## Description {#description}

For this use case, if the value in Google Sheets is less than 50, then an image with hot drinks displays. If the value is greater than or equal to 50, then an image with cold drinks displays. If there is some other value or no value at all, the player displays a default image.

## Preconditions {#preconditions}

Before you start implementing the travel center local temperature activation, learn how to set up ***Data Store***, ***Audience Segmentation*** and ***Enable Targeting for Channels*** in an AEM Screens Project.

See [Configuring ContextHub in AEM Screens](configuring-context-hub.md) for detailed information.

## Basic Flow {#basic-flow}

Follow the steps below to implement the Travel Center Local Temperature Activation use case:

1. **Populating the Google Sheets**

    1. Navigate to the ContextHubDemo Google Sheet.
    1. Add a column with **`Heading1`** with corresponding value for temperature.

   ![screen_shot_2019-05-08at112911am](assets/screen_shot_2019-05-08at112911am.png)

1. **Configuring the segments in Audiences as per the requirements**

    1. Navigate to the segments in your audience (See ***Step 2: Setting up Audience Segmentation*** in **[Configuring ContextHub in AEM Screens](configuring-context-hub.md)** page for more details).

    1. Click the **Sheets A1 1** and click **Edit**.

    1. Click the comparison property and click the configuration icon.
    1. Click **googlesheets/value/1/0** from the drop-down in **Property name**

    1. Click the **Operator** as **greater-than-or-equal** from the drop-down menu

    1. Enter the **Value** as **50**

    1. Similarly, select the **Sheets A1 2** and click **Edit**.

    1. Click the **Comparison Property - Value** and select the configuration icon.
    1. Click **googlesheets/value/1/0** from the drop-down in **Property name**

    1. Click the **Operator** as **less-than** from the drop-down menu

    1. Enter the **Value** as **50**

1. Navigate and select your channel () and click **Edit** from the action bar. In the following example, **DataDrivenWeather**, a sequential channel is used to showcase the functionality.

   >[!NOTE]
   >
   >Your channel should already have a default image and the Audiences should be pre-configured as described in [Configuring ContextHub in AEM Screens](configuring-context-hub.md).

   ![screen_shot_2019-05-08at113022am](assets/screen_shot_2019-05-08at113022am.png)

   >[!CAUTION]
   >
   >Your **ContextHub** **Configurations** using the channel **Properties** > **Personalization** tab should already be set up.

   ![screen_shot_2019-05-08at114106am](assets/screen_shot_2019-05-08at114106am.png)

1. Click **Targeting** from the editor and click **Brand** and the **Activity** from the drop-down menu and click **Start Targeting**.

   ![new_activity3](assets/new_activity3.gif)

1. **Checking the Preview**

    1. Click **Preview.** Also, open your Google Sheet and update its value.
    1. Change the value to less than 50. You can view an image of a cold drink. If the value in Google Sheets is 50 or greater, you should see an image of a hot drink.

    ![result3](assets/result3.gif)

