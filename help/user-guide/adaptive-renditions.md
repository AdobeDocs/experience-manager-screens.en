---
title: Adaptive Renditions in AEM Screens
description: This page describes Architectural Overview and Configurations for Adaptive Renditions in AEM Screens.
index: no
---

# Adaptive Renditions: Architectural Overview and Configurations {#adaptive-renditions}

## Introduction {#introduction}

Adaptive Renditions allow the devices to automatically select the best rendition for a device based on customer-defined rules. The devices will automatically download and play the most appropriate rendition of an asset based on these rules allowing customers to only focus on designing the *main* experience.

## Objective {#objective}

As an AEM Screens Developer, you can now configure device-specific asset renditions to be downloaded and played automatically without having to create all content variations manually. You must configure the Adaptive Renditions before a content Author can use this feature in an AEM Screens channel.

## Architectural Overview {#architectural-overview}

Adaptive Renditions are based on the idea of having multiple asset renditions named following a specific naming convention. The decision to play a specific rendition is made by evaluating media query expressions that can only be resolved on devices with expected capabilities. 

The ability of having an associated rendition naming pattern defines a rendition mapping rule, such as portrait or landscape, as shown in the figure below. After computing all available expressions the Screens player will collect the naming patterns corresponding to the matching rules. The patterns are used to find the correct renditions during the sequence playback by looking for the patterns in the rendition names.

![image](/help/user-guide/assets/adaptive-renditions/adaptive-renditions.png)

## Configuring the Setup for using Adaptive Renditions {#setup-adaptive-renditions}

To enable the Adaptive Renditions feature, the following mapping rules should be present and the Context-Aware (CA) Configuration should be resolvable for channels and displays. 

>[!NOTE]
>To learn more about Content-Aware Configurations, see [here](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html).

Follow the steps below to configure the setup:

1. Navigate to **CRXDE Lite**. Check, if the **rendition-mapping** configuration exists in `JCR`, as shown in the figure below.

   >[!NOTE]
   >All the latest feature packs have this node structure pre-populated.

   ![image](/help/user-guide/assets/adaptive-renditions/mapping-rules1.png)

1. Ensure the Screens project has the rendition mapping configuration associated with it.

   * Every new project created with the Screens project wizard will contain a reference pointing to **rendition-mapping** configuration.

      ![image](/help/user-guide/assets/adaptive-renditions/mapping-rules2.png)

   * In an older version of Screens projects, you need to explicitly define the association by adding `sling:configRef` property pointing at `/conf/screens` to the project content node.

      ![image](/help/user-guide/assets/adaptive-renditions/mapping-rules3.png)

## Setting up Author and Publish {#setup-author-publish}

Consider the following recommendations in Author and Publish prior to using Adaptive Renditions:

* Rendition mapping has to be replicated manually.

* Asset renditions are not replicated by default. All relevant assets need to be replicated manually.

## Adding Rendition Mapping Rules {#add-rendition-mapping-rules}

1. To add a mapping rule you need to create a node of type `nt:unstructured` under the **rendition-mapping** node.

1. Add the expression property with the value containing the query expression.

   >[!NOTE]
   >Refer to [Using Media Query Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) to learn more.

1. Add the pattern property with the value containing the rendition naming pattern that will be selected, if the expression is evaluated to true.

   ![image](/help/user-guide/assets/adaptive-renditions/mapping-rules4.png)


## The Next Steps {#next-steps}

Once you have configured and uploaded the renditions, as  a Content Author, you can now use Adaptive Renditions and also migrate your devices for large networks to avail this feature, in your AEM Screens channels. See [Using Adaptive Renditions](/help/user-guide/using-adaptive-renditions.md) for more details.
