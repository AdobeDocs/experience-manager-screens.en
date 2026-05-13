---
title: Support Monitoring
description: Learn about Support Monitoring for AEM Screens Best Practices Guide.
exl-id: b9d6f713-e26d-4f56-bedb-2d419a19a05c
TQID: https://experienceleague.adobe.com/uqtkwa1zcJ58tJOxWT0gWkOhAM-C-5zEdcFLjrHa1-Q
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
    internal-label: Experience Manager Screens
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
---
# Support Monitoring {#support-monitoring}

This section provides best practices related to managing device and content anomalies in a digital signage project.

Support monitoring includes:

* **Device Monitoring**
* **Content Monitoring**

## Content Monitoring {#content-monitoring}

Content monitoring lets you troubleshoot the issues related to content not properly displayed on the screen:

1. If a blank screen issue is encountered:

   * Check the *preview* so you can see if the channel is showing a black screen.
   * Register a *local Chrome player* (as an extension) on your laptop to that display and see if that shows a black screen.
   * Right-click and inspect and check the *applicable logs*.

   Also, if the issue is not happening on the local player but only on the device:

   * Check the *media type* (being used) that may have issues on that device and also confirm if the content was successfully downloaded locally (admin UI clear channel cache).
   * Include any *device logs* in the ticket for quick troubleshooting.
   * *Collect logs* from the device from AEM.
 
## Device Monitoring {#device-monitoring}

Device monitoring related to monitoring the physical device if you encounter a blank screen issue:

1. If a blank screen issue is encountered:

   * Check if the *display* is powered on.
   * Check if the *computer* is powered on and is sending a signal.
   * Right-click, inspect, and check *applicable logs*.
