---
title: Using Adaptive Renditions in AEM Screens
description: This page describes how to use Adaptive Renditions in AEM Screens.
index: no
---
# Using Adaptive Renditions in AEM Screens {#adaptive-renditions}

## Introduction {#introduction}

Adaptive Renditions allow the devices to automatically select the best rendition for a device based on customer-defined rules. The devices will automatically download and play the most appropriate rendition of an asset based on these rules allowing customers to only focus on designing the *main* experience.

## Objective {#objective}

As an AEM Screens Content Author, you can now configure device-specific asset renditions to be downloaded and played automatically without having to create all content variations manually.
Once a Developer adds the rendition mapping properties and rules, you are now ready to apply the rendition mapping to assets and subsequently include those in an AEM Screens channel.

>[!IMPORTANT]
>Before you start using Adaptive Renditions, in an AEM Screens channel, it is recommended to learn about this feature's Architectural Overview and Configuration. See [Adaptive Renditions: Architectural Overview and Configurations](/help/user-guide/adaptive-renditions.md) for more details.

## Migration Strategy {#migration-strategy}

>[!IMPORTANT]
>For large networks, it is recommended that the migration is done gradually to mitigate the risks as the feature will introduce changes in the manifest and file storage format. 

The following diagram depicts the migration strategy for large networks:

![image](/help/user-guide/assets/adaptive-renditions/migration-strategy1.png)

To enable the feature, add at least one mapping rule and make sure the rendition mapping configuration is resolvable in the context of displays and channels. Follow the steps below to migrate:

1. Add [Rendition Mapping Rules](/help/user-guide/adaptive-renditions.md).
1. Create a folder for new channels and add a reference pointing at the rendition mapping configuration.
1. Create new channels replacing the old ones and upload renditions.
1. Reassign displays to the new channels.
1. Add a reference to the migrated displays or locations pointing at the rendition mapping configuration.
1. Repeat steps 3, 4, and 5 for all remaining channels and displays.

   >[!NOTE]
   >After completing the migration, ensure to remove all configuration references from channels, displays, and locations and add a single one to the project content node.

## Uploading Renditions and using Adaptive Renditions in an AEM Screens Channel {#upload-renditions}

1. Create a version of the asset which better suits the signage display, for example, `portrait orientation`.

1. Choose the rendition naming pattern, for example,`portrait`.

1. Rename the asset file so it contain the pattern, for example, `my_asset_portrait.png`.

1. Click on **Add Rendition** to upload the rendition, as shown in the figure below.

   ![image](/help/user-guide/assets/adaptive-renditions/add-rendition.png)