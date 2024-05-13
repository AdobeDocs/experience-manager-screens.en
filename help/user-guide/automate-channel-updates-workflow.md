---
title: Use a workflow to automate asset updates for an AEM Screens channel
description: Learn how to create a workflow to automatically process assets uploaded to Adobe Experience Manager and dynamically assign them to a Screens channel.
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: developing
feature: Developing Screens
role: Developer
level: Intermediate
---

# Use a workflow to automate asset updates for an AEM Screens channel {#automate-channel-updates-workflow}

Learn how to create a workflow to automatically process assets uploaded to Adobe Experience Manager and dynamically assign them to a Screens channel. In this example, a workflow is triggered when an image is added to a specific folder. The workflow applies a dynamic text overlay (watermark process) and assigns the image to a Screens channel. Lessons learned from this example can be applied to a wide variety of automation scenarios.

## Prerequisites {#prerequisites}

To complete this tutorial the following is needed:

1. [AEM 6.5](https://experienceleague.adobe.com/en/docs/experience-manager-65)
1. [AEM Service Pack 8 or higher](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/release-notes/release-notes)
1. [AEM 6.5 Screens FP7 or higher](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/release-notes/release-notes-fp-202103)

## Quick setup {#quick-setup}

The below video illustrates how to install a sample code package that introduces a new workflow to Adobe Experience Manager. This feature allows a user to update the properties of a folder in AEM Assets to point to a Screens channel. Whenever an image is added to that folder, it is added to the specified AEM Screens channel.

>[!VIDEO](https://video.tv.adobe.com/v/333174/?quality=12&learn=on)

1. Download the compiled code package: **[screens-demo.all-2.0.0-SNAPSHOT.zip](./assets/screens-demo.all-2.0.0-SNAPSHOT.zip)**
1. Install the above package using AEM Package Manager.

## Workflow model {#workflow-model}

A custom folder metadata schema was created to capture the target Screens channel that images should be added. Two workflow models are used to automate the asset processing. The **DAM Update Asset** workflow is edited to call a custom workflow, **Screens Demo Asset Processing that inspects the asset's containing folder to determine the target Screens channel. The **Screens Demo Asset Processing** workflow is also responsible for applying the watermark to the image.

>[!VIDEO](https://video.tv.adobe.com/v/333175/?quality=12&learn=on)

## Custom workflow process steps {#workflow-process-step}

Inspect two custom workflow process steps that are used as part of the **Screens Demo Asset Processing** workflow.

>[!VIDEO](https://video.tv.adobe.com/v/333179/?quality=12&learn=on)

The `AssetProcessingCheck.java` custom workflow is a process that performs a check on the workflow's payload. It determines if the payload is an asset and if the containing folder is configured to point to a AEM Screens channel. If the requirements are met, the process step persists two properties, `screen-channel` and `asset-path`, to the workflow's metadata.

The `AddAssetToChannel.java` custom workflow is a process step that inspects the workflow's metadata and updates the AEM Screens channel to reference the image.

1. Download the source code: **[screens-demo-main.zip](./assets/screens-demo-main.zip)**
1. Unzip and view the code using your favorite IDE.
