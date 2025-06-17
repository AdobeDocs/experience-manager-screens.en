---
title: AEM Platform Configurations
description: The page describes AEM Platform Configurations
exl-id: cfe1769b-4da2-430d-a7b1-10dbcaf9f51b
---
# AEM Platform Configurations {#platform-configurations}

>[!NOTE]
>
>A typical stakeholder for this activity is an AEM Implementor.

Get started with AEM Screens by following the sections below to set up AEM platform configurations

## Server Configurations {#server-configurations}

To set up server configurations, see [Server Configurations](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/configuring-screens-introduction#ServerConfiguration).

## Author-Publish {#author-publish}

See [Configuring Author and Publish in AEM Screens](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish).

>[!NOTE]
>
>If there is only one Author and one Publish, you can only follow the steps under **Setting up Replication Agents on Author** in [Configuring Author and Publish in AEM Screens](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish) page.

## Dispatcher Configurations {#dispatcher-configurations}

Dispatcher is Adobe Experience Manager's caching and load-balancing tool. Using AEM's Dispatcher also helps to protect your AEM server from attack. Therefore, you can increase the security of your AEM instance by using the Dispatcher with an enterprise-class web server.

See **[Dispatcher Configurations for AEM Screens](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens)** that highlights guidelines for configuring Dispatcher for an AEM Screens project.

## Installing FFMpeg and Video Renditions {#installing-ffmpeg}

Install FFMpeg following the steps for the appropriate OS (usually RHEL):

1. If installing by enabling EPEL and RPMFusion, you can install all the gstreamer codecs to broaden support for FFmpeg conversions
1. If the AAC codec is marked as experimental, ffmpeg conversions fail. To avoid this issue, add `-strict -2` to the video profiles (`/etc/dam/video` in AEM 6.3 and moved to `/libs/settings/dam/video in AEM 6.4`)

   >[!NOTE]
   >
   >The `-strict -2` must be the last parameter in the list of parameters. Also, in AEM 6.4, copy the nodes under */libs/settings/dam/video* to */conf/global/settings/dam/video* as mentioned in [Video Renditions](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/authoring/product-features/generating-renditions).
1. Verify that video conversions are happening and that renditions are being created.

## Password Restrictions {#password-restrictions}

The password policy of AEM must be disabled on the AMS instance. It can also be alternately configured in the web console using the Screens device service *com.adobe.cq.screens.device.impl.DeviceService*
See **Password Restrictions** section in[Configuring Author and Publish in AEM Screens](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/author-publish/author-and-publish)

## Setting up the Environments {#setting-up-environments}

Install and run the most current versions of the following packages for your version of Adobe Experience Manager (AEM):

* AEM Service Pack
* Screens Feature Pack
* AEM Cumulative Fix Pack

In addition to the above, identify any development packages (for example, WCM Core
components) or third-party toolkits (for example, SAP Hybris) that are required.
Install the same software packages in your local development environment. Instruct your client to adopt the same configuration on all of their QA, Stage, and Production servers. Mismatched server configurations create problems when deploying and testing.

>[!NOTE]
>
>To install the latest Feature Pack for AEM Screens, see [Release Notes](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/aem-screens-introduction).

## Setting up ACLs {#setting-up-acls}

Setting up ACLs explains how to segregate projects so that each individual or team handles their own project.

See [Setting up ACLs](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/setting-up-acls) for more details.
