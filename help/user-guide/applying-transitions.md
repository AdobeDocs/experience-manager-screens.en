---
title: Applying Transitions
seo-title: Applying Transitions
description: Follow this page to learn how to apply transitions to your Screens projects.
seo-description: Follow this page to learn how to apply transitions to your Screens projects.
uuid: b79d521b-19d4-47c8-a41a-148d7bbf6ac9
contentOwner: jsyal
---

# Applying Transitions {#applying-transitions}

This section describes how you can apply the **Transition** component in-between different assets (images and videos) in a channel.


>[!CAUTION]
>
>To learn in detail about the properties for the Transition component, refer to [Transitions](adding-components-to-a-channel.md#transition).

## Adding Transition Component to Assets in a Channel {#adding-transition}

Follow the steps below to add a transition component to your AEM Screens project:

>[!NOTE]
>
>**Prerequisites**
> Create an AEM Screens project **TestProject** 
with a channel **TestTransition**. Additionally, set up a location and a display to view the 
 output.

1. Navigate to the Channel **TestTransition** and click **Edit** from the action bar.

   ![image1](assets/transitions1.png)

   >[!NOTE]
   >
   >The **TestTransition** channel already has few assets (images and videos) in it. For example, the **TestTransition** channel includes three images and two videos, as shown below:
   
   ![image2](assets/transitions2.png)
   

1. Drag and drop the **Transition** component to your editor.
   >[!CAUTION]
   >
   >Before you add the transition to your assets in your channel, make sure you do not add transition before the first asset in the sequential channel. The first item in your channel must be an asset and not a transition.

   ![image3](assets/transitions3.png)

   > [!NOTE]
   >
   >By default, the properties of the transition component such as **Type** is set to **Normal** and the **Duration** is set to *600 ms*.  Additionally,  it is not advisable to set a transition duration time that is longer than the asset it is being applied to.
 
## Adding Transition Component to Videos in a Channel {#adding-transition-videos}

When applying transition component between videos, always set the **Type** to **Fade** and the **Sequence Duration** to **1600 ms**.

![image3](assets/transitions4.png)