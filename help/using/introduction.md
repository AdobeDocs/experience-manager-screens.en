---
title: Introduction to [!UICONTROL AEM Screens]
seo-title: Best Practices Guide for [!UICONTROL AEM Screens] Projects
description: This page is an introductory section to AEM Screens
seo-description: This page provides an introduction to AEM Screens
---

# Introduction to AEM Screens {#introduction}

**AEM (Adobe Experience Manager) Screens** is a Digital Signage Solution that allows you to author, publish and play dynamic and interactive digital experiences involving different types of in-venue display screens in concert with a comprehensive omnichannel digital marketing strategy.

AEM Screens allows you to create:

* **dedicated digital menu boards**
* **product recommenders**
* **background lifestyle imagery**

Additionally, Screens provide many unique applications for customers and employees based on the domain where these are deployed, such as:

* **interactive displays**
* **wayfinding**
* **branding**
* **adding ambience to your environment**

Creating and managing a digital signage network using AEM Screens is simple and intuitive. A player application hosts content channels built for AEM Screens by customers or implementation partners. *Locations* manage a pre-defined location hierarchy and contains displays. Each *display* has a dashboard that shows different devices and screens attached. Content for AEM Screens is managed in *channels*. *AEM Screens Player* renders content present within channels onto displays.



>[!NOTE]
>
>To learn in detail about different features in an AEM Screens project development and management, refer to **[AEM Screens User Guide](https://helpx.adobe.com/experience-manager/6-5/screens/user-guide.html)**.

## AEM Sites versus AEM Screens {#aem-sites-screens}

> [!NOTE]
>
> If your implementation team has experience working with AEM Sites applications, it is important to understand the difference between AEM Sites and AEM Screens.

AEM Screens provides a unified Authoring/Playback platform for deploying content to digital signage devices in public spaces. While the experience author should strive to maintain consistency across the web and in-venue channels, there are some differences that should be noted.

* **Dwell-time**: Typically, web pages are designed to provide a wealth of information that can be consumed over a relatively longer period of time. In contrast, in-venue digital experiences should anticipate the needs of the viewer and provide clear and concise directions for how and why the user should engage. This results in experiences that are more targeted, curated and contextual.

* **Viewing Distance**: Viewing distances are generally longer or further away than the typical viewing distance users experience with a web site. As a result, text size should normally be larger and the spacing between text, images and other complimentary content should be tested based on the anticipated screen size and placement in the physical space.

* **Persistence**: The connected state of the player device should never be allowed to influence whether or not digital experiences are delivered to the user. The player must be designed so that one or more experiences always persist and can be delivered regardless of the connected state of the player device.

* **Media Loop Segmentation**: Configuring each player device to have its own loop segment ensures that localized content can be easily authored, published and played within the overall digital experience. Media assets contained within embedded sequence channels are added to the previous loop segment and offer the opportunity to target a media loop segment for each location grouping.

* **Interactive Experiences**: A touch enabled, kiosk application can be authored and delivered in a Screens channel using AEM and the SPA editor. It is a best practice to apply consistent omnichannel design properties, an inactivity timer to reset the experience and a clear call to action for what tasks the application can execute. The landing page should consist of key digital elements designed to convey value, attract the user to the screen and prompt the user to engage.

AEM Screens provides a framework to deploy content to physical devices. Content is assigned to Channels in Screens, which can contain media content or touch screen applications. Within this framework, an AEM Sites application could be delivered as content through a Channel.

Before being dropped into a Channel in Screens, an AEM Sites must be formatted for use at the dimensions of the display device it is intended for.

> [!NOTE]
>
> Many AEM Sites components are not compatible with AEM Screens. AEM Screens comes with many of its own out-of-the-box components allowing you to build digital experiences without requiring customization. If project requirements allow, use built-in AEM Screens functionality where possible.
