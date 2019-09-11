---
title: AEM Sites versus AEM Screens
seo-title: AEM Sites versus AEM Screens
description: The page describes differences between AEM Sites and AEM Screens.
seo-description: The page highlights the differences between AEM Sites and AEM Screens.
---

# AEM Sites versus AEM Screens {#aem-sites-screens}

> [!NOTE]
>
> If your implementation team has experience working with AEM Sites applications, it is important to understand the difference between AEM Sites and AEM Screens.

AEM Screens provides a framework to deploy content to physical devices. Content is assigned
to Channels in Screens, which can contain media content or touch screen applications. Within
this framework, an AEM Site application could be delivered as content through a Channel.
Regardless of the complexity of the Site application, it will not override the entities defined in
AEM Screens. The Channels and Displays defined in AEM Screens effectively provide a
container to deliver the Site application to physical devices.

Before being dropped into a Channel in Screens, an AEM Site must be formatted for use at the
dimensions of the display device it is intended for.

> [!NOTE]
>
> Many AEM Sites components are not compatible with AEM Screens. AEM Screens comes with many of its own out-of-the-box components allowing you to build digital experiences without requiring customization. If project requirements allow, use built-in AEM Screens functionality where possible.
