---
title: Auto Registration of Players
description: Follow this page so you can learn about auto registration of Players with AMS/On-Prem Screens.
feature: Administering Screens, Players
role: Admin
level: Intermediate
exl-id: 28449523-a44d-4260-9771-f1987686cbb6
TQID: https://experienceleague.adobe.com/uvCRS49L6CQbah4AKFwRdhGN-pvKnTWtNMN8CnFojIQ
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
    internal-label: Experience Manager Screens
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
---
# Auto Registration of Players {#auto-registration}

Bulk registering thousands of players manually can become cumbersome and adds time and cost. To simplify this process, the bulk registration feature lets you specify a pre-shared key in AEM that can be provisioned into a player either through a configuration file or a Mobile Device Management (MDM) solution.

## Implementing Auto Registration of Players {#bulk-registering-implementation}

Follow the steps below to implement auto registration of players:

1. Log in to your AEM instance and click your AEM Screens project and click **Properties** from the action bar.
1. Click the **Advanced** tab so you can view the **Device registration** section.

1. Specify an auto registration code in the **Bulk registration code** field. Then an optional default display in the **Default display assignment** to assign to the player that is auto registered.

   >[!NOTE]
   >Enter a code of your choice and click a default display if needed.

   ![image](/help/user-guide/assets/auto-registration/auto-register1.png)
1. Provision your players with the appropriate server URL and registration code using an MDM or configuration JSON file. 

   >[!NOTE]
   >See the implementation page for the specific player for your Operating System (OS) for more details. You can also use the admin UI for entering the registration code.

1. If the `registrationKey` attribute matches the one configured in AEM, the player automatically registers itself and if a default display is configured, that content downloads and plays.

    ![image](/help/user-guide/assets/auto-registration/auto-register2.png)

## Security Best Practices {#security-best-practices}

Follow the section below to consider some of the best practices for Security:

* Ensure that the registration code is not compromised &ndash; Configure the code in AEM just before starting the bulk registration and when done, clear that field, and save in AEM.

* You can configure the path `/bin/screens/registration` so that it is accessible only from known IP ranges, if possible.

* Consider using an MDM to provision the player with the configuration. 

* Always use `HTTPS` and not `HTTP` for player communication with AEM.

   >[!NOTE]
   >Default display assignment currently only works for bulk registration. It does not work for manual registration when a registration code is unavailable.
