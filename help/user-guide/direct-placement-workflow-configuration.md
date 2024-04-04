---
title: Direct Placement Workflow Configuration 
seo-title: Direct Placement Workflow Configuration
description: This page highlights Direct Placement Workflow Configuration.
seo-description: This page highlights Direct Placement Workflow Configuration.

---

# Direct Placement Workflow Configuration {#direct-placement-workflow}

Follow this page to learn about configuring an asset workflow that allows you to programmatically insert an asset to a pre-defined AEM Screens channel.

This section covers the following topics:

* Overview
* Configuring Direct Placement Workflow

## Overview {#overview}

Direct Placement Workflow Configuration maps an AEM Screens project channel to a specific folder in assets and allows for placement of any asset in that folder. It is recommended to trigger bulk offline update in order to complete the publication.

Alternatively, as a content author you can manually click **Update Offline Content**.

>[!NOTE]
>
>To learn how to use bulk offline update, refer to [Content Update As a Service](/help/user-guide/content-update-as-a-service.md).

## Configuring Direct Placement Workflow {#configuring-workflow}

>[!IMPORTANT]
>
>Before you start the configuration, you must install the [Demo  Package](https://github.com/godanny86/screens-demo/releases/download/v.0.0.1/screens-demo.all-1.0-SNAPSHOT.zip). Once you have installed the package, you should be able to view and access it from your AEM instance > Tools (icon) > **Workflow** > **Workflow Models**.

Follow the steps below to configure the direct placement workflow:

1. Navigate to AEM Screens from your your AEM instance and create a Screens project titled as **Asset Workflow**.

1. Create a channel titled as **Workflow-Assets** under **Channels** folder.

