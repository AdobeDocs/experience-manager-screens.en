---
title: Configure Screens Replication Agents
description: Follow this page to get information on how to configure Screens Replication Agents.
role: Developer
level: Intermediate
---

# Configuring Screens Replication Agents {#configuring-screens-replication-agent}

This following page describes how to configure Screens Replication Agents.

## Objective {#objective}

The Screens Replication Agent is responsible for bringing ping data from publish to author. It is essential to configure this so that the author can show the device ping.

>[!NOTE]
>To learn more about Screens Replication Agents, see [Screens Replication Agents and Commands](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/administering/author-publish/author-publish-architecture-overview.html?lang=en#screens-replication-agents-and-commands).

You must complete both the sections to complete the configuration for Screens Replication Agent:

1. [Enabling Users and Updating the Password](#enable-users)
1. [Updating Settings for Screens Replication Agent](#replicate-agent)

## Enabling Users and Updating the Password {#enable-users}

Follow the steps below to enable users and update the password for screens-receiver-user:

>[!NOTE]
>For security reasons, it is recommended to avoid using the admin password for screens-receiver-user.

1. Navigate  to your AEM Author instance.

1. Click on tools --> **Security** --> **Users**.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1.png)

1. Search for **screens-receiver-user**.

1. Select the **screens-receiver-user** and click on **Enable** from the action bar.

   ![image](/help/user-guide/assets/screens-replication/screens-replication2.png)

1. Click on **OK** to confirm.

   ![image](/help/user-guide/assets/screens-replication/screens-replication3.png)

   Once you have enabled the user, you will see the **screens-receiver-user** as **Enabled** under the **Status** field.

   ![image](/help/user-guide/assets/screens-replication/screens-replication4.png)

1. Select the **screens-receiver-user** and click on **Properties** from the action bar.

   ![image](/help/user-guide/assets/screens-replication/screens-replication5.png)

1. Click on **Change Password** under **Account settings** from the **Details** tab, as shown in the figure below.

   ![image](/help/user-guide/assets/screens-replication/screens-replication6.png)

1. Enter a new password in the **Change Password** dialog box and click on **Save**.

   >[!NOTE]
   >You should enter the existing admin user password in **Your Password** field.

   ![image](/help/user-guide/assets/screens-replication/screens-replication7.png)

1. Click on **Save & Close**.

1. Select the **screens-receiver-user** and click on **Activate** from the action bar.

   ![image](/help/user-guide/assets/screens-replication/screens-replication8.png)

1. Click on **OK** to confirm.

   ![image](/help/user-guide/assets/screens-replication/screens-replication9.png)

1. Select the **screens-receiver-user** and click on **Disable** from the action bar.

   >[!IMPORTANT]
   > Disabling **screens-receiver-user** only disables this user from the author instance and all the users in the publish instance still remain active. Do not click on **Deactivate** from the action bar, as deactivating will remove the user from the publish instances too.

   ![image](/help/user-guide/assets/screens-replication/screens-replication10.png)

1. Click on **OK** to confirm.

## Updating Settings for Screens Replication Agent {#replicate-agent}

Follow the section below to update settings in Screens Replication agent:

>[!IMPORTANT]
>You must complete the following steps on ALL existing screens replication agents.

1. Navigate to your AEM instance.

1. Click on tools --> **Deployment** --> **Replication**.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1a.png)

1. Click on **Agents on author**.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1b.png)

1. Search for the Screens Replication agent on author and click the link, as shown in the figure below.

   >[!NOTE]
   >Search for the Screens Replication agent with the letter **S** included in the name of the author.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1c.png)

1. Click on **Edit**.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1d.png)

1. Check **Enabled** from the **Settings** tab.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1e.png)

1. Navigate to **Transport** tab from the **Agent Settings** dialog box and update the **User** to **screens-receiver-user** and enter the same password that you set before in step (8) of [Enabling Users and Updating the Password](#enable-users).

   ![image](/help/user-guide/assets/screens-replication/screens-replication1-f.png)

1. Click on **OK**.

1. Once you complete the preceding steps, you can click on **Test Connection** to verify the connection.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1g.png)

   If the connection verification is successful, you have completed configuring Screens Replication Agent.