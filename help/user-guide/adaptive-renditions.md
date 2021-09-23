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

## Adding Rendition Mapping Property to the Screens Project {#rendition-mapping-new}

To enable the Adaptive Renditions feature, the following mapping rules should be present and the Context-Aware (CA) Configuration should be resolvable for channels and displays. 

>[!NOTE]
>To learn more about Content-Aware Configurations, see [here](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html).

Follow the steps below to configure the setup:

1. Navigate to **CRXDE Lite**. Check, if the **rendition-mapping** configuration exists in `/conf/screens/sling:configs/rendition-mapping`, as shown in the figure below.

   >![image](/help/user-guide/assets/adaptive-renditions/mapping-rules1.png)

   >[!IMPORTANT]
   >If you installed the latest Feature Pack 202109, you will see **rendition-mapping** node structure pre-populated in `/conf/screens/sling:configs/rendition-mapping` in CRXDE Lite. See [Release Notes for Feature Pack 202109](/help/user-guide/release-notes-fp-202109.md) to get details on the latest feature pack.
   >For existing projects, ensure that Screens project has the **rendition-mapping** configuration associated. See [Adding Rendition Mapping to an Existing Project](#rendition-mapping-existing) section to learn more.

### Adding Rendition Mapping Property to an Existing Project {#rendition-mapping-existing}

1. Navigate to **CRXDE Lite**.

1. Explicitly define the rendition mapping association by adding `sling:configRef` property pointing at `/conf/screens` to the project content node, as shown in the figure below.

   ![image](/help/user-guide/assets/adaptive-renditions/renditon-mapping2.png)


## Setting up Author and Publish {#setup-author-publish}

Consider the following recommendations in Author and Publish prior to using Adaptive Renditions:

* Rendition mapping has to be replicated manually.

* Asset renditions are not replicated by default. All relevant assets need to be replicated manually.

## Adding Rendition Mapping Rules {#add-rendition-mapping-rules}

Follow the steps below to add a node under Rendition Mapping:

1. Navigate to this path `/conf/screens/sling:configs/rendition-mapping` from **CRXDE Lite**.

1. Create a node under **rendition-mapping**. Right click on **rendition-mapping** and click on **Create** --> **Create Node**, as shown in the figure below.

   ![image](/help/user-guide/assets/adaptive-renditions/add-node1.png)

1. Enter the **Name** for your mapping rule such as **rule1** and the node **Type** as **nt:unstructured** in **Create Node** dialog box. Click on **OK**.

   ![image](/help/user-guide/assets/adaptive-renditions/add-node2.png)


1. You need to add the expression property with the value containing the query expression.

   >[!NOTE]
   >Refer to [Using Media Query Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) to learn more.

   Click on **rule1** that you created, and enter **expression** in **Name** and **(orientation:landscape)** in **Value**, as shown below. Click on **Add**.

   ![image](/help/user-guide/assets/adaptive-renditions/add-node3.png)

   

1. Add the pattern property with the value containing the rendition naming pattern that will be selected, if the expression is evaluated to true.

   To add the pattern property, click on **rule1** that you created, and enter **pattern** in **Name** and **landscape** in **Value**, as shown below. Click on **Add**. 

   ![image](/help/user-guide/assets/adaptive-renditions/add-node4.png)

1. Click on **Save All** and you will see the properties under the node you created under **rendition-mapping**.

   ![image](/help/user-guide/assets/adaptive-renditions/add-node5.png)


## The Next Steps {#next-steps}

Once you have configured and uploaded the renditions, as  a Content Author, you can now use Adaptive Renditions and also migrate your devices for large networks to avail this feature, in your AEM Screens channels. See [Using Adaptive Renditions](/help/user-guide/using-adaptive-renditions.md) for more details.
