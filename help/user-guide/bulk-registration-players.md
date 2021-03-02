---
title: Bulk Registration of Players
seo-title: Bulk Registration of Players
description: Follow this page to learn about Bulk Registration of Players with AMS/On-Prem Screens.
---

# Bulk Registration of Players {#bulk-registration}

Bulk registering thousands of players manually can become very cumbersome and adds time and cost. To simplify this process, the bulk registration feature allows you to specify a pre-shared key in AEM that can be provisioned into a player either through a configuration file or an Mobile Device Management (MDM) solution.

## Implementing Bulk Registration of Players {#bulk-registering-implementation}

Follow the steps below to implement bulk registration of players:

1. Log into your AEM instance and select your AEM screens project and click properties and the Advanced tab.
1. You should see a bulk registration section where you can specify a bulk registration code and an optional default display to assign to the player that is bulk registered
1. Enter a code of your choice and select a default display if needed
1. Provision your players with the appropriate server URL and registration code using an MDM or configuration JSON file. Please refer to the implementation page for the specific player for your OS for exact details. You can also use the admin UI for entering the registration code.
1. If the `registrationKey` attribute matches the one configured in AEM, the player will automatically register itself and if a default display is configured, that content will download and play.

## Security Best Practices {#security-best-practices}

Follow the section below to consider some of the best practices for Security:

* To ensure that the registration code is not compromised, configure the code in AEM just before starting the bulk registration and when done, please clear that field and save in AEM.

* You can configure that the path `/bin/screens/`registration can only be accessed from known IP ranges if possible.

* Consider using an MDM to provision the player with the configuration. 

* Always use `HTTPS` and not `HTTP` for player communication with AEM.

   >[!NOTE]
   >Default display assignment currently only works for bulk registration and not for manual registration without a registration code.