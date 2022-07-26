---
title: Dispatcher Configurations for AEM Screens
seo-title: Dispatcher Configurations for AEM Screens
description: This page highlights guidelines for configuring dispatcher for an AEM Screens project.
seo-description: This page highlights guidelines for configuring dispatcher for an AEM Screens project.
feature: Administering Screens
role: Developer, User
level: Intermediate
exl-id: 8b281488-f54d-4f8a-acef-ca60fa2315ed
---
# Dispatcher Configurations for AEM Screens{#dispatcher-configurations-for-aem-screens}

Dispatcher is Adobe Experience Manager's caching and/or load balancing tool.

The following page provides the guidelines for configuring dispatcher for an AEM Screens project.

>[!NOTE]
>
>If a dispatcher is available, connections to the registration servlet can be prevented by filtering in the dispatcher rules.
>
>If there is no dispatcher, disable the registration servlet in the OSGi components listing.

Before you configure dispatcher for an AEM Screens project, you must have prior knowledge of Dispatcher.
Refer to [Configuring Dispatcher](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html) for more details.
   
## Configuring Dispatcher for Manifest Version v2 {#configuring-dispatcher}

>[!IMPORTANT]
>The following Dispatcher configurations apply only to Manifest version v2. Refer to [Dispatcher Configurations for Manifest version v3](#configuring-dispatcherv3) for manifest version v3.

AEM Screens players or devices use authenticated session to access the resources in the publish instances as well. So, when you have multiple publish instances, the requests should always go to the same publish instance so that the authenticated session is valid for all the requests coming from the AEM Screens players/devices.

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

## Configuring Dispatcher for Manifest Version v3{#configuring-dispatcherv3}

Please make sure to allow these filters and cache rules in dispatchers fronting the publish instances for functioning of Screens.

### Pre-requisites for Manifest Version v3{#prerequisites3}

Please ensure that you follow these two prerequisites before configuring Dispatcher (manifest version v3) for AEM Screens:

* Make sure that you are using `v3 manifests`. Navigate to `https://<server:port>/system/console/configMgr/com.adobe.cq.screens.offlinecontent.impl.ContentSyncCacheFeatureFlag` and ensure that `Enable ContentSync Cache` is unchecked.

* Make sure dispatcher flush agent is configured at `/etc/replication/agents.publish/dispatcher1useast1Agent` in publish instance.

   ![image](/help/user-guide/assets/dispatcher/dispatcher-1.png)

   ![image](/help/user-guide/assets/dispatcher/dispatcher-3.png)

### Filters  {#filter-v3}

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
#/0221 { /type "allow" /method '(GET|HEAD)' /url "/content/experience-fragments/*" } ## uncomment this, if you're using experience-fragments
/0222 { /type "allow" /extension '(css|eot|gif|ico|jpeg|jpg|js|gif|pdf|png|svg|swf|ttf|woff|woff2|html|mp4|mov|m4v)' /path "/content/dam/*" } ## add any other formats required for your project here
 
## # Enable clientlibs proxy servlet
/0230 { /type "allow" /method "GET" /url "/etc.clientlibs/*" }
```

### Cache Rules {#cache-rules-v3}

* Add `/allowAuthorized "1"` to `/cache` section in `publish_farm.any`.

* All the Screens players will use authenticated session to connect to AEM (author/publish). Out-of-the-box Dispatcher does not cache these urls, so we should enable those.

* Add `statfileslevel "10"` to `/cache` section in `publish_farm.any`
   This will support caching up to 10 levels from the cache docroot and invalidate accordingly when content is published rather than invalidating everything. Feel free to change this level based on how deep your content structure is

* Add the following to `/invalidate section in publish_farm.any`

   ```
   /0003 {
       /glob "*.json"
       /type "allow"
   }
   ```

* Add the following rules to `/rules` section in `/cache` in `publish_farm.any` or in a file that is included from `publish_farm.any`:

   ```
   ## Don't cache CSRF login tokens
   /0001
       {
       /glob "/libs/granite/csrf/token.json"
       /type "deny"
       }
   ## Allow Dispatcher Cache for Screens channels
   /0002
       {
           /glob "/content/screens/*.html"
           /type "allow"
       }
   ## Allow Dispatcher Cache for Screens offline manifests
   /0003
       {
       /glob "/content/screens/*.manifest.json"
       /type "allow"
       }
   ## Allow Dispatcher Cache for Assets
   /0004
       {
  
       /glob "/content/dam/*"
       /type "allow"
       }
   ## Disable Dispatcher Cache for Screens devices json
   /0005
       {
       /glob "/home/users/screens/*.json"
       /type "deny"
       }
   ## Disable Dispatcher Cache for Screens svc json
   /0006
       {
       /glob "/content/screens/svc.json"
       /type "deny"
       }
   ```

### Add invalidation rule for segments.js {#invalidsegmentjs}

   If you are adding new segments and publishing them, the `segments.js` file served by the dispatcher doesn't have the new entries which was breaking the targeting flow on the screens device. The segments.js file is getting cached at the dispatcher level, but there was no invalidation rule for the same. As a result you must add an invalidation rule.

* Add new segments to the `/conf/<project-name>/settings/wcm/segments.seg.js` file.

* Add an invalidation rule to `/etc/httpd/conf.dispatcher.d/available_farms/999_ams_publish_farm.any`. Here is the rule to add:

```
    /invalidate {
                        .
                        .
                        /0004 {
                               /glob "conf/personalisation-hub/settings/wcm/.js"
                               /type "allow"
                        }
                }
```

* This rule ensures the `segments.js` file is invalidated and latest is fetched when modified.
