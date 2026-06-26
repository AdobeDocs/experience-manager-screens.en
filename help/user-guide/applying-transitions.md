---
title: Applying Transitions
description: Learn how to apply transitions to your AEM Screens projects.
contentOwner: jsyal
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 757e6751-8008-487f-be89-9f53ac898928
TQID: https://experienceleague.adobe.com/t4JTCyQhe7kb5v-dveK4Np9dAAGLBeatCN2kyTM6ELc
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
    internal-label: Experience Manager Screens
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a5fd0e22-1a77-4f49-a6af-7a57fff19aed
    internal-label: Authoring Screens
subfeature_v2:
  - id: e8696a6a-4caa-4059-b0b2-3fbb66f5ab7e
    internal-label: Screens projects
  - id: f5973e90-a5a3-4b84-8602-ee120d4ce9b1
    internal-label: Content
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
---
# Applying Transitions {#applying-transitions}

>[!IMPORTANT]
>This content is valid for AEM on-premise/AMS (AEM 6.5LTS and AEM 6.5). For AEM as a Cloud Service Screens content refer to the [AEM as a Cloud Service guide](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

This section describes how you can apply the **Transition** component in-between different assets (images and videos) and embedded sequences in a channel.

>[!CAUTION]
>
>To learn in detail about the properties for the **Transition** component, see [Transitions](adding-components-to-a-channel.md#transition).

## Adding Transition Component to Assets in a Channel {#adding-transition}

Follow the steps below to add a transition component to your AEM Screens project:

>[!NOTE]
>
>**Prerequisites**
>
>Create an AEM Screens project **TestProject** with a channel **TestTransition**. Also, set up a location and a display to view the output.

1. Navigate to the Channel **TestTransition** and click **Edit** from the action bar.

   ![image1](assets/transitions1.png)

   >[!NOTE]
   >
   >The **TestTransition** channel already has a few assets (images and videos) in it. For example, the **TestTransition** channel includes three images and two videos, as shown below:
   
   ![image2](assets/transitions2.png)
   

1. Drag and drop the **Transition** component to your editor.

   >[!CAUTION]
   >
   >Before you add the transition to your assets in your channel, make sure you do not add the transition before the first asset in the sequential channel. The first item in your channel must be an asset and not a transition.

   ![image3](assets/transitions3.png)

   >[!NOTE]
   >
   >By default, the properties of the transition component such as **Type** is set to **Fade** and the **Duration** is set to *1600 milliseconds*. Also, it is not advisable to set a transition duration time that is longer than the asset it is being applied to.

1. Also, if you add an **Embedded Sequence** component (that includes a sequence channel) to this channel editor, you can add a transition component at the end. Doing so ensures that the content plays in the correct order, as seen in the following image:

   ![image3](assets/transitions5.png)

