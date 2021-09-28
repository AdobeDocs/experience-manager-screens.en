---
title: Using Adaptive Renditions in AEM Screens
description: This page describes how to use Adaptive Renditions in AEM Screens.
exl-id: e7f68ed4-73c3-492a-b33a-dd915ef1f8be
---
# Using Adaptive Renditions in AEM Screens {#adaptive-renditions}

## Introduction {#introduction}

Adaptive Renditions allow the devices to automatically select the best rendition for a device based on customer-defined rules. The devices will automatically download and play the most appropriate rendition of an asset based on these rules allowing customers to only focus on designing the *main* experience.

## Objective {#objective}

As an AEM Screens Content Author, you can now configure device-specific asset renditions to be downloaded and played automatically without having to create all content variations manually.
Once a Developer adds the rendition mapping properties and rules, you are now ready to apply the rendition mapping to assets and subsequently include those in an AEM Screens channel.

>[!IMPORTANT]
>Before you start using Adaptive Renditions, in an AEM Screens channel, it is recommended to learn about this feature's Architectural Overview and Configuration. See [Adaptive Renditions: Architectural Overview and Configurations](/help/user-guide/adaptive-renditions.md) for more details.

## Using Adaptive Renditions in Channels {#using-adaptive-renditions}

>[!NOTE]
>Once you have added [rendition mapping property to the Screens Project](/help/user-guide/adaptive-renditions.md#rendition-mapping-new) and [rendition mapping rules](/help/user-guide/adaptive-renditions.md#add-rendition-mapping-rules), as a Content Author you are now ready to apply the renditions to your assets.

### Applying Renditions to Assets {#apply-renditions-assets}

Follow the steps below to apply renditions to the assets, that you want to use in tour Screens channel:

1. Navigate to the **Assets** folder in your AEM instance.

1. Create a version of the asset which better suits the signage display, for example, `seahorse.jpg`.

1. Choose the rendition naming pattern, for example,`landscape`, similar to  what was defined in **pattern** property in **CRXDE Lite**. Refer to [Adding Rendition Mapping Rules](/help/user-guide/adaptive-renditions.md#add-rendition-mapping-rules) for more details.

1. Click on **Add Rendition** to upload the rendition, as shown in the figure below.

   ![image](/help/user-guide/assets/adaptive-renditions/manage-pub-asset2.png)

1. Select the renamed the asset file. The rendition that you are adding must contain the pattern (defined in step 3), for example, `seahorse-landscape.png`.

1. Once you have added the asset, select the asset and click on **Manage Publication** from the action bar to publish the asset.

   ![image](/help/user-guide/assets/adaptive-renditions/manage-pub-asset1.png)

   >[!NOTE]
   >Refer to [On-Demand Content Update](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/authoring/content-updates/on-demand-content.html?lang=en) to learn more about  managing Publication and delivering content updates from Author to Publish to device.


## Migration Strategy {#migration-strategy}

>[!IMPORTANT]
>For large networks, it is recommended that the migration is done gradually to mitigate the risks as the feature will introduce changes in the manifest and file storage format. Adding the `sling:configRef` to the entire project involves having all players updated to Feature Pack 6.5.9. In case, you updated some of the players, you need to add the `sling:configRef` only to those displays, locations, or channel folders that have all players updated to Feature Pack 6.5.9.

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
