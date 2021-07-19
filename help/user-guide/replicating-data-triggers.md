---
title: Replicate data-triggers to publish servers
seo-title: Replicate data-triggers to publish server
description: Follow this page to learn how to replicate data triggers to publish server.
seo-description: Replicate data-triggers to publish server.
feature: Administering Screens, Data Trigger
role: Developer
level: Intermediate
exl-id: 6f90b864-eaa0-4b74-a47e-b0967a550552
---
# Replicating Data Triggers to Publish Servers {#replicating-data-triggers}

When using ContextHub and AEM Targeting Engine to customize content based on data triggers in an author/publish setup, all the ContextHub and Personalization related configurations are not automatically replicated with the channels when they are published.

Follow this page to learn the manuals steps required to publish these configurations separately.

This basically comes down to manually publishing:

1. ContextHub Store and UI modules configurations
1. Personalization audiences
1. Personalization activities

## Steps for Replicating Data Triggers to Publish Server {#replicating-data-triggers-publish}

Follow the steps below to replicate the data triggers to publish server.

### Step 1: Replicating ContextHub Configurations {#replicating-contexthub-configurations}

1. Navigate to **Tools** > **Deployment** > **Distribution** > **Publish Agent** and click on the publish agent to configure your settings.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers1.png)

   >[!NOTE]
   >
   >Alternatively, you can use the `http://localhost:4502/libs/granite/distribution/content/distribution-agent.html?agentName=publish` to navigate to the screen directly to configure and test the connection.

1. Click **Test Connection** from the action bar to validate the communication of the author with the publish instance, as shown in the figure  below.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers2.png)

   >[!NOTE]
   >
   >If the test fails, you need to fix the replication agent configuration between the author and publish instance. Refer to [Troubleshooting Test Connection](/help/user-guide/replicating-data-triggers.md#troubleshoot-test) for more details.

1. Select **Add** from the **Distribution Agent** screen tree and select the configuration path for your project, for example, `/conf/screens/settings/cloudsettings/configuration`.

1. Click **Submit**.

### Replicating the Audiences {#replicating-audiences}

1. Navigate to your AEM instance > **Personalization** > **Audiences** or use `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/audiences.html` to navigate direcly.

1. Drill down into your project folder, for example, `/conf/screens/`.

   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers10.png)

1. Select all audiences and segments from the the user interface.

1. Click **Manage Publication** from the action bar.

1. Click **Next** and **Publish**.

### Replicating the Activities  {#replicating-activities}

1. Navigate to your AEM instance > **Personalization** > **Activities** or use `http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html` to navigate direcly.

1. Drill down into your project folder, that is, `/content/campaigns/screens/…`.

1. Select all activities from the user interface.

1. Click **Manage Publication** from the action bar.

1. Click **Next** and **Publish**.

>[!IMPORTANT]
>
>Replicating ContextHub configurations and audiences is done during the project setup, while replicating activities and will be required every time targeting is changed inside a channel.

#### Result {#result}

If replication is successful, you should view the following structure on the publish instance (or similar for your project):

`/conf/screens/settings/cloudsettings/configuration/…`
`/conf/screens/settings/wcm/segments/…`
`/content/campaigns/screens/…`

## Troubleshooting Test Connection {#troubleshoot-test}

If the test connection fails while replicating the ContextHub configurations, follow the section below for troubleshooting the issue:

1. Navigate to Tools > **Deployment** > **Distribution** > **Publish Agent**.

1. Click **Edit** from the action bar and ensure the endpoint URL in **Importer Endpoints** field is also pointing to the publish server URL in Distribution Agent.
   ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers9.png)

1. If you not using the default admin credentials, then you need to configure the distribution agent with a different username and password.

   Follow the steps below:

   1. Navigate to Tools > **Operations** > **Web Console** `http://localhost:4502/system/console/configMgr`to open the **Adobe Experience Manager Web Console screen**.
   1. Search for **Apache Sling Distribution Transport Credentials - User Credentials based DistributionTransportSecretProvider**

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers6.png)

   1. Create a configuration, by populating **Name**, **User name** and **password**, for example, *slingTransportSecretProvider*.

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers7.png)

   1. Click **Save**
   1. Use `Cmd +F` to search for **Apache Sling Distribution Agent - Forward Agents Factory** to open the configurations and search for for **Transport Secret Provider**.

      ![image1](/help/user-guide/assets/replicating-triggers/replicating-triggers8.png)

   1. Update the `(name=default)` with `(name=slingTransportSecretProvider)`.
   1. Click **Save** and run the test connection again from the **Distribution Agent** screen from your AEM instance again.
