---
title: Configuring and Deploying AEM Screens
description: The AEM Screens Player is available for Android&trade;, Chrome OS, iOS, and Windows. Learn about the configuration and deployment of AEM Screens.
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
docset: aem65
role: Admin
level: Intermediate
exl-id: 8cf4240c-1d6c-441d-b8a0-f01516455543
---
# Configuring and Deploying AEM Screens {#configuring-and-deploying-aem-screens}

This page shows how to install and configure the Screens players on your devices.

## Server Configuration {#server-configuration}

>[!IMPORTANT]
>
>AEM Screens Player does not use the Cross-Site Request Forgery (CSRF) token. Therefore, to configure the AEM server to be ready to use for AEM Screens, skip the referrer filter by allowing empty referrers.

## Health Check Framework {#health-check-framework}

The Health Check Framework lets the user check if two necessary configurations are set up before running an AEM Screens project. 

It allows the user to verify the following two configuration checks to run an AEM Screens project, that is, to check the state of the following two filters:

1. **Allow Empty Referrer**
2. **https**

Follow the steps below to check if these two vital configurations are enabled for AEM Screens:

1. Navigate to [Adobe Experience Manager Web Console Sling Health Check](http://localhost:4502/system/console/healthcheck?tags=screensconfigs&overrideGlobalTimeout=).

   ![assets](assets/health-check1.png)


2. Click **Execute the selected health checks** so you can run the validation for two properties listed above.

   If both the filters are enabled, then the **Screens Configuration Health Service** shows the **Result** as **OK** with both the configurations as enabled.

   ![assets](assets/health-check2.png)

   If one or both the filters are disabled, then an alert is displayed for the user, as shown in the figure below.

   The following alert showcases if both the filters are disabled:
    ![assets](assets/health-check3.png)

>[!NOTE]
>
>* To enable the **Apache Sling Referrer Filter**, see [Allow Empty Referrer Requests](/help/user-guide/configuring-screens-introduction.md#allow-empty-referrer-requests).
>* To enable the **HTTP** service, see [Apache Felix Jetty Based HTTP Service](/help/user-guide/configuring-screens-introduction.md#allow-apache-felix-service).

### Prerequisites {#prerequisites}

The following key points below helps to configure and AEM server to be ready to use for AEM Screens.

#### Allow Empty Referrer Requests {#allow-empty-referrer-requests}

1. Navigate to **Adobe Experience Manager Web Console Configuration** by way of AEM instance > hammer icon > **Operations** > **Web Console**.

   ![image](assets/config/empty-ref1.png)

1. **Adobe Experience Manager Web Console Configuration** opens. Search for sling referrer.

   For searching the sling referrer property, press **Command+F** for **Mac** and **Control+F** for **Windows**.

1. Check the **Allow Empty** option, as shown in the figure below.

    ![image](assets/config/empty-ref2.png)
    
1. Click **Save** to enable the Apache Sling Referrer Filter Allow Empty.


#### Apache Felix Jetty Based HTTP Service {#allow-apache-felix-service}

1. Navigate to **Adobe Experience Manager Web Console Configuration** by way of AEM instance > hammer icon > **Operations** > **Web Console**.

   ![image](assets/config/empty-ref1.png)

1. **Adobe Experience Manager Web Console Configuration** opens. Search for Apache Felix Jetty Based HTTP Service.

   For searching this property, press **Command+F** for **Mac** and **Control+F** for **Windows**.

1. Check the **ENABLE HTTP** option, as shown in the figure below.

   ![image](assets/config/config-1.png)

1. Click **Save** to enable the *Http* service.

#### Enable Touch UI for AEM Screens {#enable-touch-ui-for-aem-screens}

AEM Screens requires TOUCH UI and does not work with the Classic UI of Adobe Experience Manager (AEM).

1. Navigate to `*<yourAuthorInstance>/system/console/configMgr/com.day.cq.wcm.core.impl.AuthoringUIModeServiceImpl*`
1. Ensure that the **Default authoring UI mode** is set to **TOUCH**, as shown in the figure below

Alternatively, you can also perform the same setting using yourAuthorInstance *>* tools (hammer icon) > **Operations** > **Web Console** and search for **WCM Authoring UI Mode Service**.

![screen_shot_2018-12-04at22425pm](assets/screen_shot_2018-12-04at22425pm.png)

>[!NOTE]
>
>You can always enable Classic UI for specific users using user preferences.

#### AEM in NOSAMPLECONTENT run mode {#aem-in-nosamplecontent-runmode}

Running AEM in production uses the **NOSAMPLECONTENT** run mode. Remove the *X-Frame-Options=SAMEORIGIN* header (in the additional response header section) from

`https://localhost:4502/system/console/configMgr/org.apache.sling.engine.impl.SlingMainServlet`.

This removal is required for the AEM Screens Player to play online channels.

#### Password Restrictions {#password-restrictions}

With the latest changes to ***DeviceServiceImpl***, you do not have to remove the password restrictions.

You can configure ***DeviceServiceImpl*** from the link below to enable password restriction while creating the password for the screen device users:

`https://localhost:4502/system/console/configMgr/com.adobe.cq.screens.device.impl.DeviceService`

Follow the steps below to configure ***DeviceServiceImpl***:

1. Navigate to **Adobe Experience Manager Web Console Configuration** by way of your AEM instance > hammer icon > **Operations** > **Web Console**.

1. **Adobe Experience Manager Web Console Configuration** opens. Search for `*deviceservice*`. For searching the property, press **Command+F** for macOS and **Control+F** for Microsoft&reg; Windows.

![screen_shot_2019-07-31at92058am](assets/screen_shot_2019-07-31at92058am.png)

#### Dispatcher Configuration {#dispatcher-configuration}

To learn how to configure Dispatcher for an AEM Screens project, see [Configuring Dispatcher for an AEM Screens project](dispatcher-configurations-aem-screens.md).

#### Java&trade; encoding {#java-encoding}

Set the ***Java&trade; encoding*** to Unicode. For example, `*Dfile.encoding=Cp1252*` does not work.

>[!NOTE]
>
>Use HTTPS for AEM Screens Server in production use.
