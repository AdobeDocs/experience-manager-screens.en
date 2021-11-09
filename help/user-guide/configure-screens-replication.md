---
title: Configure Screens Replication Agent
description: Follow this page to get information on how to configure Screens Replication Agent.
role: Developer
level: Intermediate
---

# Configuring Screens Replication Agent {#configuring-screens-replication-agent}

This section describes how to configure Screens replication agent.

## Enabling Users and Updating the Password {#enable-users}

Follow the steps below:

1. Navigate  to your AEM instance.

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
   >You should enter **admin** in **Your Password** field.

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

## Updating Screens Replication Agent {#replicate-agent}

Follow the section below to update settings in Screens Replication agent:

1. Navigate to your AEM instance.

1. Click on tools --> **Deployment** --> **Replication**.

   ![image](/help/user-guide/assets/screens-replication/screens-replication1a.png)
