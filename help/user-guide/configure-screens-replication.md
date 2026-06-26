---
title: Configure Screens Replication Agents
description: Learn about how to configure Screens Replication Agents.
role: Developer
level: Intermediate
exl-id: 40877547-5027-41eb-8d66-d4a2d7b9af70
TQID: https://experienceleague.adobe.com/ms01oXXn6BqzkscgjG0o0g1pq-wEawpMy1eel6Uz1uM
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
    internal-label: Experience Manager Screens
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
---
# Configuring Screens Replication Agents {#configuring-screens-replication-agent}

>[!IMPORTANT]
>This content is valid for AEM on-premise/AMS (AEM 6.5LTS and AEM 6.5). For AEM as a Cloud Service Screens content refer to the [AEM as a Cloud Service guide](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

This following page describes how to configure Screens Replication Agents.

## Objective {#objective}

The Screens Replication Agent is responsible for bringing commands data such as *user*, *password*, *rebootSchedule*, *maxNumberOfLogFilesToKeep*, and many more such values from publish to author. It is essential to configure this agent so that the author can show the device ping.

>[!NOTE]
>To learn more about Screens Replication Agents, see [Screens Replication Agents and Commands](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/author-publish/author-publish-architecture-overview#screens-replication-agents-and-commands).

Complete both the sections if you want to complete the configuration for Screens Replication Agent:

1. [Enabling Users and Updating the Password](#enable-users)
1. [Updating Settings for Screens Replication Agent](#replicate-agent)

## Enabling Users and Updating the Password {#enable-users}

Follow the steps below to enable users and update the password for `screens-receiver-user`:

>[!NOTE]
>For security reasons, it is recommended to avoid using the admin password for `screens-receiver-user`.

1. Navigate to your instance of AEM Author.

1. Click tools > **Security** > **Users**.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1.png)

1. Search for **`screens-receiver-user`**.

1. Click the **`screens-receiver-user`** and click **Enable** from the action bar.

   ![image](/help/user-guide/assets/screens-replication/screens-replication2.png)

1. Click **OK** to confirm.

   ![image](/help/user-guide/assets/screens-replication/screens-replication3.png)

   When you have enabled the user, you see the **`screens-receiver-user`** as **Enabled** under the **Status** field.

   ![image](/help/user-guide/assets/screens-replication/screens-replication4.png)

1. Click the **`screens-receiver-user`** and click **Properties** from the action bar.

   ![image](/help/user-guide/assets/screens-replication/screens-replication5.png)

1. Click **Change Password** under **Account settings** from the **Details** tab, as shown in the figure below.

   ![image](/help/user-guide/assets/screens-replication/screens-replication6.png)

1. Enter a new password in the **Change Password** dialog box and click **Save**.

   >[!NOTE]
   >Enter the existing admin user password in **Your Password** field.

   ![image](/help/user-guide/assets/screens-replication/screens-replication7.png)

1. Click **Save & Close**.

1. Click the **`screens-receiver-user`** and click **Activate** from the action bar.

   ![image](/help/user-guide/assets/screens-replication/screens-replication8.png)

1. Click **OK** to confirm.

   ![image](/help/user-guide/assets/screens-replication/screens-replication9.png)

1. Click the **`screens-receiver-user`** and click **Disable** from the action bar.

   >[!IMPORTANT]
   > Disabling **`screens-receiver-user`** only disables this user from the Authoring instance and all the users in the Publishing instance remain active. Do not click **Deactivate** from the action bar, as deactivating removes the user from the Publishing instances too.

   ![image](/help/user-guide/assets/screens-replication/screens-replication10.png)

1. Click **OK** to confirm.

## Updating Settings for Screens Replication Agent {#replicate-agent}

Follow the section below to update settings in the AEM Screens Replication agent:

>[!IMPORTANT]
>Complete the following steps on ALL existing AEM Screens Replication Agents.

1. Navigate to your AEM instance.
1. Click tools > **Deployment** > **Replication**.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1a.png)

1. Click **Agents on author**.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1b.png)

1. Search for the all AEM Screens Replication Agents on author and click the link, as shown in the figure below.

   >[!NOTE]
   >Search for all AEM Screens Replication Agents. The Screens Replication Agent name includes the letter **S** in the title.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1c.png)

1. Click **Edit**.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1d.png)

1. Check **Enabled** from the **Settings** tab.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1e.png)

1. Navigate to **Transport** tab from the **Agent Settings** dialog box and update the **User** to **`screens-receiver-user`** and enter the same password that you set before in step (8) of [Enabling Users and Updating the Password](#enable-users).

   ![image](/help/user-guide/assets/screens-replication/screens-replication1-f.png)

1. Click **OK**.

1. After you complete the preceding steps, click **Test Connection** to verify the connection.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1g.png)

   If the connection verification is successful, you have completed configuring the Screens Replication Agent.

