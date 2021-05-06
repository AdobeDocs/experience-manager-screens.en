---
title: Use workflow to automate asset updates for an AEM Screens channel
seo-title: Use workflow to automate asset updates for an AEM Screens channel
description: Learn how to create a workflow to automatically process assets uploaded to Adobe Experience Manager and dynamically assign them to a Screens channel. In this example when an image is added to a specific folder, a workflow is triggered that applies a dynamic watermark and assigns the image to a Screens channel. Lessons learned from this example can be applied to a wide variety of automation scenarios.
seo-description: Learn how to create a workflow to automatically process assets uploaded to Adobe Experience Manager and dynamically assign them to a Screens channel. In this example when an image is added to a specific folder, a workflow is triggered that applies a dynamic watermark and assigns the image to a Screens channel. Lessons learned from this example can be applied to a wide variety of automation scenarios.
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: developing
feature: Developing Screens
role: Developer
level: Intermediate
---

# Use workflow to automate asset updates for an AEM Screens channel {#automate-channel-updates-workflow}

Learn how to create a workflow to automatically process assets uploaded to Adobe Experience Manager and dynamically assign them to a Screens channel. In this example when an image is added to a specific folder, a workflow is triggered that applies a dynamic watermark and assigns the image to a Screens channel. Lessons learned from this example can be applied to a wide variety of automation scenarios.

## Prerequisites {#prerequisites}

To complete this tutorial the following is needed:

1. [AEM 6.5](https://experienceleague.adobe.com/docs/experience-manager-65.html)
1. [AEM Service Pack 8 or greater](https://experienceleague.adobe.com/docs/experience-manager-65/release-notes/service-pack/sp-release-notes.html)
1. [AEM 6.5 Screens FP7 or greater](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/release-notes/release-notes-fp-202103.html)

## Quick setup {#quick-setup}

The below video illustrates how to install a sample code package that will introduce a new workflow to Adobe Experience Manager. This feature allows a user to update the properties of a folder in AEM Assets to point to a Screens channel. Whenever an image is added to that folder it will be added to the specified screens channel.

>[!VIDEO](https://video.tv.adobe.com/v/333174/?quality=12&learn=on)

1. Download the compiled code package: **[screens-demo.all-2.0.0-SNAPSHOT.zip](./assets/screens-demo.all-2.0.0-SNAPSHOT.zip)**
1. Install the above package using AEM Package Manager.

## Workflow model {#workflow-model}

A custom folder metadata schema was created to capture the target Screens channel that images should be added. Two workflows models are used to automate the asset processing. The **DAM Update Asset** workflow is modified to call a custom workflow, **Screens Demo Asset Processing** which will inspect the asset's containing folder to determine the target Screens channel. The **Screens Demo Asset Processing** workflow is also responsible for applying the watermark to the image.

>[!VIDEO](https://video.tv.adobe.com/v/333175/?quality=12&learn=on)

## Custom workflow process steps {#workflow-process-step}

Inspect two custom workflow process steps that are used as part of the **Screens Demo Asset Processing** workflow.

>[!VIDEO](https://video.tv.adobe.com/v/333179/?quality=12&learn=on)

`AssetProcessingCheck.java` is a custom workflow process that performs a check on the workflow's payload to determine if the payload is an asset and if the containing folder is configured to point to a Screens channel. If the requirements are met, the process step persists two properties, `screen-channel` and `asset-path`, to the workflow's metadata.

`AddAssetToChannel.java` is a custom workflow process step that inspects the workflow's metadata and updates the Screens channel to reference the image.

1. Download the source code: **[screens-demo-main.zip](./assets/screens-demo-main.zip)**
1. Unzip and view the code using your favorite IDE.
