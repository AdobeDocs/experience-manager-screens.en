---
title: Environments for [!UICONTROL AEM Screens]
description: Learn more about the environments for an AEM Screens project.

---

# Environments {#environments}

Determine in advance which AEM environments the client has and is expecting you to use, both for *development* and *deployment*.

>[!NOTE]
>
>AEM Screens requires several packages for projects to function. All environments should be running the same version of Adobe Experience Manager.

Follow the guidelines below to set up the environment for your AEM Screens project:

1. Run the most current versions of the following packages for your version of Adobe Experience Manager:

   * **AEM Service Pack**
   * **Screens Feature Pack**
   * **AEM Cumulative Fix Pack**

1. Identify any development packages (for example, WCM Core components) or third-party tool kits (for example, SAP Hybris) that are required.

1. Install the same software packages in your local development environment.

1. Instruct your client to adopt the same configuration on all of their QA, Stage, and Production servers. Mismatched server configurations create problems when deploying and testing.
