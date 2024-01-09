---
title: Release Notes for Screens Feature Pack 202401
description: Follow this page to get information for AEM Screens Feature Pack 202401 released on Jan 2, 2024.
feature: Feature Pack
role: Developer
level: Intermediate
---
# Release Notes for Feature Pack 202401 {#release-notes-for-screens-security-feature-pack}

>[!CAUTION]
>It is recommended that you upgrade to the latest version of 6.5 Adobe Experience Manager (AEM 6.5).

## Availability {#availability}

AEM Screens released AEM 6.5 Feature Pack 11.1 .

You can download the latest feature pack for AEM Screens 6.5.11.1 Release from the [Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) using your Adobe ID. Navigate to **Adobe Experience Manager** tab and search for **Screens** to get the latest feature pack titled as **AEM 6.5 Screens FP11.1**.

## Release Date {#release-date}

The Release Date for AEM Screens Feature Pack 202204 is Jan 02, 2024.

### What's New {#what-is-new}

This release includes security fixes only.

### Bug Fixes {#bug-fixes}

* XSS issue at AEM Screens device "Idle text" field. (SCRNS-2614)

* XSS issue at `screens/dashboard/device.html` via the `Clear cache` action dialog. (SCRNS-2632)

* XSS issue in screens player configuration at `libs/screens/player/browser/firmware.html`. (SCRNS-2652)

* Stored XSS in devices title triggers when a device is deleted. (SCRNS-2653)

* XSS issue at `/libs/screens/core/components/device/info.json.html`. (SCRNS-2659)

* Reflected XSS with the parameter `item` at `/screens/register-device-wizard.html`. (SCRNS-2670)

* Reflected XSS in `screens/dashboard/device.html` via the `returnPage` parameter. (SCRNS-3056)

* Open Redirect on assign-device-wizard.html. (SCRNS-3444)

* Open Redirect on device dashboard. (SCRNS-3443)

* XSS issue at `libs/screens/dcc/components/clientlibs/actions/cq.screens.dcc.openLink.js`. (SCRNS-3459)

* Fixed, Missing Recurrence Schedule and Add Schedule Buttons: A Problem Discovered in Channel Scheduling. (SCRNS-2739)

#### AEM Screens Player Downloads  {#aem-screens-player-downloads}

To download the latest AEM Screens player, refer to **[AEM Screens Player Downloads](https://download.macromedia.com/screens/index.html)**.
