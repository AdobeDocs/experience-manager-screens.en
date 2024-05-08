---
title: Support Monitoring
description: Learn about Support Monitoring for AEM Screens Best Practices Guide.
exl-id: b9d6f713-e26d-4f56-bedb-2d419a19a05c
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
   * Register a *local chrome player* (as an extension) on your laptop to that display and see if that shows a black screen.
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
