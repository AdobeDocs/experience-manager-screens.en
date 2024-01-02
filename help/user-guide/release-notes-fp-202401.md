---
title: Release Notes for Screens Security Feature Pack 202401
description: Follow this page to get information for AEM Screens Security Feature Pack 202401 released on Jan 2, 2024.
feature: Security Feature Pack
role: Developer
level: Intermediate
---
# Release Notes for Feature Pack 202401 {#release-notes-for-screens-security-feature-pack}

>[!CAUTION]
>It is recommended that you upgrade to the latest version of Adobe Experience Manager (AEM). Screens provides maintenance support for AEM 6.3 Screens platform.

## Availability {#availability}

AEM Screens released AEM 6.5 Feature Pack 11.1.

You can download the latest feature pack for AEM Screens 6.5.11.1 Release from the [Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) using your Adobe ID. Navigate to **Adobe Experience Manager** tab and search for **Screens** to get the latest feature pack titled as **AEM 6.5 Screens FP11**.

## Release Date {#release-date}

The Release Date for AEM Screens Feature Pack 202204 is Jan 02, 2024.

### Bug Fixes {#bug-fixes}

* Stored XSS in AEM Screens device "Idle text" field. This is now fixed.

* Stored XSS at `screens/dashboard/device.html` via the `Clear cache` action dialog. This is now fixed.

* Stored XSS in screens player configuration at `libs/screens/player/browser/firmware.html`. This is now fixed.

* Stored XSS in devices title triggers when a device is deleted. This is now fixed.

* AMS XSS - /libs/screens/core/components/device/info.json.html. This is now fixed.

* Reflected XSS with the parameter `item` at `https://author-bugbounty-65-prod.adobecqms.net/screens/register-device-wizard.html`. This is now fixed.

* Reflected XSS in `screens/dashboard/device.html` via the `returnPage` parameter. This is now fixed.

* Open Redirect on assign-device-wizard.html. This is now fixed.

* Open redirect at returnPage parameter. This is now fixed.

* Stored XSS in `libs/screens/dcc/components/clientlibs/actions/cq.screens.dcc.openLink.js`.  This is now fixed.

#### AEM Screens Player Downloads  {#aem-screens-player-downloads}

To download the latest AEM Screens player and learn more about the bug fixes, refer to **[AEM Screens Player Downloads](https://download.macromedia.com/screens/index.html)**.
