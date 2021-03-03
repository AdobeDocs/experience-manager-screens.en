---
title: Using MDM or EMM to bulk provision Android Player
seo-title: Bulk Provisioning of Android Player using EMM or MDM
description: Follow this page to learn about Bulk Provisioning of Android Player using EMM or MDM
---

# Bulk Provisioning of Android Player using Enterprise Mobility Management {#bulk-provisioning}

When deploying the Android player in bulk, it becomes tedious to manually register every single player with AEM. It is highly recommended to use an EMM (Enterprise Mobility Management) solution such as VMWare Airwatch, MobileIron or Samsung Knox to remotely provision and manage your deployment. AEM Screens Android player supports the industry standard EMM AppConfig to allow for remote provisioning. 

## Implementing Bulk Provisioning of Android Player using Enterprise Mobility Management {#implementation}

Follow the steps below to allow bulk provisioning in Android Player:

1. Ensure your Android device supports Google Play services.
1. Enroll your Android player devices with your favorite EMM solution that supports AppConfig. 
1. Log into your EMM console and pull the AEM Screens Player application from Google Play.
1. Select managed configuration (or related option).
1. You should now see a list of player options that can be configured (such as server and bulk registration code).
1. Configure these parameters, save, and deploy the policy to the devices.

   >[!NOTE]
   >The devices should receive the application along with the configuration and point to the correct AEM server with the selected configuration. If you chose to configure the bulk registration code and kept it the same as configured in AEM, the player should be able to automatically register itself. If you had configured a default display, it can also download and show some default content (which can later be changed as per your convenience).

Additionally, you should check with your EMM vendor on AppConfig support. Most popular ones such as [VMWare Airwatch](https://docs.samsungknox.com/admin/uem/vm-configure-appconfig.htm), [Mobile Iron](https://docs.samsungknox.com/admin/uem/mobileiron2-configure-appconfig.htm), [SOTI](https://docs.samsungknox.com/admin/uem/soti-configure-appconfig.htm), [Blackberry UEM](https://docs.samsungknox.com/admin/uem/bb-configure-appconfig.htm), [IBM Maas360](https://docs.samsungknox.com/admin/uem/ibm-configure-appconfig.htm) and [Samsung Knox](https://docs.samsungknox.com/admin/uem/km-configure-appconfig.htm) support this industry standard.


