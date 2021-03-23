---
title: Dispatcher Configurations for AEM Screens
seo-title: Dispatcher Configurations for AEM Screens
description: This page highlights guidelines for configuring dispatcher for an AEM Screens project.
seo-description: This page highlights guidelines for configuring dispatcher for an AEM Screens project.
feature: Administering Screens
role: "Developer, Business Practitioner"
level: Intermediate
---

# Dispatcher Configurations for AEM Screens{#dispatcher-configurations-for-aem-screens}

Dispatcher is Adobe Experience Manager's caching and/or load balancing tool.

The following page provides the guidelines for configuring dispatcher for an AEM Screens project.

>[!NOTE]
>
>If a dispatcher is available, connections to the registration servlet can be prevented by filtering in the dispatcher rules.
>
>If there is no dispatcher, disable the registration servlet in the OSGi components listing.

## Pre-requisites {#pre-requisites}

Before you configure dispatcher for an AEM Screens project, you must have prior knowledge of Dispatcher.

Refer to [Configuring Dispatcher](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html) for more details.

## Configuring Dispatcher {#configuring-dispatcher}

AEM Screens players/devices use authenticated session to access the resources in the publish instances as well. So, when you have multiple publish instances, the requests should always go to the same publish instance so that the authenticated session is valid for all the requests coming from the AEM Screens players/devices.

Follow the steps below to configure dispatcher for an AEM Screens project.

### Enabling Sticky Sessions {#enable-sticky-session}

If you want to use multiple publish instances fronted by single dispatcher, you will have to update the `dispatcher.any` file to enable stickiness

``` xml
/stickyConnections {
  /paths
  {
    "/"
  }
 }
```

If you have one publish instance fronted by one dispatcher, enabling the stickiness at the dispatcher will not help as the load balancer may send each request to dispatcher. In this case, click on **Enable** in **Stickiness** field to enable it at your load balancer level, as shown in the figure below:

![image](/help/user-guide/assets/dispatcher/dispatcher-enable.png)

For example, if you are using AWS ALB, refer to [Target groups for your Application Load Balancers](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html) for enabling stickiness at the ALB level. Enable the stickiness for 1 day.

### Step 1: Configuring Client Headers {#step-configuring-client-headers}

Add the following to `/clientheaders`section:

**X-Requested-With**

**X-SET-HEARTBEAT**

**X-REQUEST-COMMAND**

### Step 2: Configuring Screens Filters {#step-configuring-screens-filters}

To configure Screens filters, add the following to ***/filter***.

```
## AEM Screens Filters
## # Login, Ping and Device Configurations
/0200 { /type "allow" /method "POST" /url "/libs/granite/core/content/login.validate/j_security_check" }
/0201 { /type "allow" /method "GET" /url "/libs/granite/csrf/token.json" }
/0202 { /type "allow" /method "GET" /url "/content/screens/svc.json" }
/0203 { /type "allow" /method "GET" /url "/content/screens/svc.ping.json" }
/0204 { /type "allow" /method "GET" /url "/content/screens/svc.config.json" }
## # Device Dashboard Configurations
/0210 { /type "allow" /method '(GET|POST)' /url "/home/users/screens/*/devices/*/profile_screens.preferences.json" }
/0211 { /type "allow" /method "POST" /url "/home/users/screens/*/devices/*/profile_screens.logs.json" }
/0212 { /type "allow" /method "POST" /url "/home/users/screens/*/devices/*/profile_screens.statusinfo.json" }
/0213 { /type "allow" /method "POST" /url "/home/users/screens/*/devices/*/profile_screens.screenshot.json" }
## # Content Configurations
/0220 { /type "allow" /method '(GET|HEAD)' /url "/content/screens/*" }
/0221 { /type "allow" /method '(GET|HEAD)' /url "/content/screens/*/jcr:content/*/offline-config_*.zip" }
/0222 { /type "allow" /method '(GET|HEAD)' /url '/var/contentsync/content/screens/.+/jcr:content/.+/offline-config_.*\.[0-9]+\.zip' }
```

### Step 3: Disabling Dispatcher Cache {#step-disabling-dispatcher-cache}

Disable dispatcher caching for ***/content/screens path***.

Screens players uses authenticated session, so the dispatcher does not cache any of the screens players requests for `channels/assets`. 

To enable the cache for the assets so that the assets are served from dispatcher cache, you must:

* Add `/allowAuthorization 1` in `/cache` section
* Add the below rules to `/rules` section of `/cache`

``` xml
/0000
    {
        /glob "*"
        /type "allow"
    }   

/0001
    {
        # Disable Dispatcher Cache for Screens channels
        /glob "/content/screens/*.html"
        /type "deny" 
    }

/0002
    {
    # Disable Dispatcher Cache for Screens offline manifests
    /glob "/content/screens/*.json"
    /type "deny"
    }

/0003
    { # Disable Dispatcher Cache for Screens devices json 
    /glob "/home/users/screens/*.json"
    /type "deny"
    }
```
