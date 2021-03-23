---
title: Auto Registration of Players
seo-title: Auto Registration of Players
description: Follow this page to learn about Auto Registration of Players with AMS/On-Prem Screens.
feature: "Administering Screens, Players"
role: Administrator
level: Intermediate
---

# Auto Registration of Players {#auto-registration}

Bulk registering thousands of players manually can become very cumbersome and adds time and cost. To simplify this process, the bulk registration feature allows you to specify a pre-shared key in AEM that can be provisioned into a player either through a configuration file or a Mobile Device Management (MDM) solution.

## Implementing Auto Registration of Players {#bulk-registering-implementation}

Follow the steps below to implement auto registration of players:

1. Log into your AEM instance and select your AEM screens project and click **Properties** from the action bar.
1. Select the **Advanced** tab to view the **Device registration** section.

1. Specify an auto registration code in **Bulk registration code** field and an optional default display in **Default display assignment** to assign to the player that is auto registered.
   >[!NOTE]
   >Enter a code of your choice and select a default display if needed.

   ![image](/help/user-guide/assets/auto-registration/auto-register1.png)
1. Provision your players with the appropriate server URL and registration code using an MDM or configuration JSON file. 

   >[!NOTE]
   >Please refer to the implementation page for the specific player for your Operating System (OS) for more details. You can also use the admin UI for entering the registration code.

1. If the `registrationKey` attribute matches the one configured in AEM, the player will automatically register itself and if a default display is configured, that content will download and play.

    ![image](/help/user-guide/assets/auto-registration/auto-register2.png)

## Security Best Practices {#security-best-practices}

Follow the section below to consider some of the best practices for Security:

* To ensure that the registration code is not compromised, configure the code in AEM just before starting the bulk registration and when done, please clear that field and save in AEM.

* You can configure the path `/bin/screens/registration` to only be accessible from known IP ranges if possible.

* Consider using an MDM to provision the player with the configuration. 

* Always use `HTTPS` and not `HTTP` for player communication with AEM.

   >[!NOTE]
   >Default display assignment currently only works for bulk registration and not for manual registration without a registration code.