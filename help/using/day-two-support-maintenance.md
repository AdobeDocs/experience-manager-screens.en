---
title: Day Two Support and Maintenance
description: Learn about Day Two support and maintenance for AEM Screens.
exl-id: 2b5511ff-c8f4-4ea3-8a65-f17f3a1ec39b
TQID: https://experienceleague.adobe.com/IMuRCxE7v8DyK-T4Q3lehhclfgGtu0VIHyIsODOpEzA
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
    internal-label: Experience Manager Screens
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Day Two Platform Support and Maintenance {#day-two-support-maintenance}

>[!IMPORTANT]
>This content is valid for AEM on-premise/AMS (AEM 6.5LTS and AEM 6.5). For AEM as a Cloud Service Screens content refer to the [AEM as a Cloud Service guide](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

AEM Screens requires several packages for projects to function. All environments must be running the same version of Adobe Experience Manager.

Follow the guidelines for support and maintenance for Day Two of the project development phase:

1. Run the most current versions of the following packages for your version of Adobe Experience Manager:

   * **AEM Service Pack**
   * **Screens Feature Pack**
   * **AEM Cumulative Fix Pack**

1. Identify any development packages (for example, WCM Core components) or third-party tool kits (for example, SAP Hybris) that are required.

1. Install the same software packages into your local development environment.

1. Instruct your client to adopt the same configuration on all of their QA, Stage, and Production servers. Mismatched server configurations create problems when deploying and testing.

