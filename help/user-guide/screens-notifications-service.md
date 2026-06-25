---
title: AEM Screens Notifications Service
description: Learn more about how you can monitor device activity for AEM Screens.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 205235d7-e621-4134-975c-257ae60939bc
TQID: https://experienceleague.adobe.com/9BVI-WKkjiL-vY57T-GMir-4Dll552q-30LDHF20BxU
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
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
---
# AEM Screens Notifications Service{#aem-screens-notifications-service}

>[!IMPORTANT]
>This content is valid for AEM on-premise/AMS (AEM 6.5LTS and AEM 6.5). For AEM as a Cloud Service Screens content refer to the [AEM as a Cloud Service guide](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

<!--removed from metadata: admitteddomains: @adobe.com;@caesars.com-->

***AEM Screens Notifications Service*** describes monitor device activity.

This section covers the following topics:

* **Overview**
* **Configuring Email Settings**
* **Email Notification**
* **Example use case**

<!-- 
OBSOLETE NOTE>
>[!CAUTION]
>
>This AEM Screens functionality is only available, if you have installed AEM 6.3.2 Feature Pack 3 or AEM 6.4.1 Screens Feature Pack 1.
>
>To get access to this Feature Pack, contact Adobe Support and request access. After you have permissions you can download it from Package Share. 
-->

## Overview {#overview}

***AEM Screens Notifications Service*** lets administrators receive an email if an AEM Screens Player does not ping for a configurable time.

This service can be configured in the OSGi web console.

## Configuring Email Settings {#configuring-email-settings}

Follow the steps below for configuring the email notification settings:

1. Open **Adobe Experience Manager Web Console Configuration**.
1. Open **Screens Device Email Monitoring Service**.

   ![screen_shot_2018-04-26at44602pm](assets/screen_shot_2018-04-26at44602pm.png)

1. Define the following fields so you can configure your settings for the email:

   **Devices Path** &ndash; Enter the path to the Screens Projects that you want to monitor. The path is usually `/home/users/screens/<Name of your project>`.

   For example, if your project is **`We.Retail`**, use the project path as ***/home/users/screens/we-retail***.

   >[!NOTE]
   >
   >Specify the project path, where the device users are located.

   **Schedule Frequency** &ndash; Specify a time (for example, 5:00 P.M. or 17:00) or frequency in hours (for example, 1) at which this monitor should send emails.

   **Ping Time out** &ndash; This field specifies the interval in minutes after which a device should be considered not reachable.

   **SMTP Server** &ndash; Specifies the SMTP Server that is used for sending emails.

   **SMTP Port** &ndash; Enter the SMTP Port.

   **Use TLS** &ndash; Transport Layer Security (TLS) lets you use a secure communication with the SMTP Server.

   Adobe recommends that you use TLS for secure connection to corporate mail servers. Check with your mail administrator for appropriate values.

   **username** &ndash; Specify the username for sending emails.

   **password** &ndash; Specify the password for sending emails.

   **Recipient** &ndash; Specify the recipient's email address.

   >[!NOTE]
   >
   >You can enter only one email address. To send a bulk email, create a group or distribution list with the relevant users.

1. Click **Save** to configure the monitor activity through an email for your AEM Screens device.

## Email Notification {#email-notification}

After you set the configuration for your email notifications, you receive an email notification that contains the link to the actual device that is reported of inactivity.

Accessing that link navigates you directly to the device dashboard.

Emails are only sent if:

* there is at least one device that has not pinged for the given ping timeout, and
* is still not pinging at the time of generating the email.

### Example Use Cases {#example-use-cases}

The following example describes a few scenarios for reference, to configure the properties from Screens Device Email Monitoring Service.

**Scenario 1**

You set the schedule frequency as 1:00 A.M. and the ping timeout as 60. Then, if your AEM Screens device does not ping between 12:00 P.M. until 1:00 P.M., you receive an email notification that confirms device inactivity.

**Scenario 2**

You set the schedule frequency as 1 and the ping timeout as 60. Then, if your AEM Screens device does not ping at once at any particular time of the day, you receive an email notification that confirms device inactivity.
