---
title: Release Notes for Feature Pack 201907
description: Learn about the AEM Screens Feature Pack 201907 that was released on July 31, 2019.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: release-notes
content-type: reference
docset: aem65
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: 6a05a014-aedf-4261-849d-abf1ce070964
TQID: 'https://experienceleague.adobe.com/fbTrzAj52dW2JuRe-6InIkh-dT52Au9pGgoAEjR7WW8'
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
    internal-label: Experience Manager Screens
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ad636d67-61fa-5d69-a17e-20f06cb716b9
    internal-label: Feature Pack
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Release Notes for Feature Pack 201907 {#release-notes-for-feature-pack}

>[!CAUTION]
>
>Adobe recommends that you upgrade to the latest version of Adobe Experience Manager (AEM). AEM Screens provides maintenance support for the AEM 6.3 Screens platform.

AEM Screens released AEM 6.4.5 Feature Pack 5 and AEM 6.5.1 Feature Pack 1 with the following details.

## Release Date {#release-date}

The Release Date for AEM Screens Feature Pack 201907 is July 31, 2019.

### What's New {#what-s-new}

* **Data Trigger drives asset change in an AEM Screens channel**

The player switches to a channel that shows emergency information. The emergency system sends this information when it receives an event. The channel plays exclusively until the emergency situation is over.


See [Emergency Channel](emergency-channel.md) use case for implementation.

* **Targeting Enabled for asynchronous components

Targeting can now be enabled for assets used in the AEM Screens project.

To learn more about how you can enable targeting for assets in the AEM Screens project, see [Configuring ContextHub in AEM Screens](configuring-context-hub.md).

After you have configured ContextHub for your AEM Screens project, follow different use cases to understand how data triggered assets plays a vital role in different industries:

**[Retail Inventory Targeted Activation](retail-inventory-activation.md)**

**[Travel Center Temperature Activation](local-temperature-activation.md)**

**[Hospitality Reservation Activation](hospitality-reservation-activation.md)**

* **Improvements in Update Handlers**

The update handler now parses the experience fragments and collects any image, video, or product associated to it.

* **Launches**

Launches let content authors create future versions of the channels. With the help of Launches, authors can preview each channel in the launch and should be able to initiate a request for review. Approvers group gets notification and can approve or reject the request. When the live date is reached, the content plays in the devices.
See [Launches](launches.md) for more details.

* **Offline Configurations in Experience Fragments**

You can now add offline configurations (client-side libraries and static files) while configuring Screens Experience Fragment. See [Using Experience Fragments](experience-fragments-in-screens.md) for more details.

### Released AEM Screens Players

The following AEM Screens Players are released for AEM 6.4.5 Feature Pack 5 and AEM 6.5.1 Feature Pack 1:

* ChromeOS
* Windows
* Android&trade;

#### AEM Screens Player Downloads

To download the latest AEM Screens Player and learn more about the bug fixes, see [AEM Screens Player Downloads](https://download.macromedia.com/screens/).
