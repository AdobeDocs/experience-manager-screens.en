---
title: Replicate data-triggers to publish servers
seo-title: Replicate data-triggers to publish server
description: Replicate data-triggers to publish server.
seo-description: Replicate data-triggers to publish server.
---

# Replicating Data Triggers to Publish Server {#replicating-data-triggers}

When using ContextHub and AEM Targeting Engine to customize content based on data triggers in an author/publish setup, all the ContextHub and Personalization related configurations are not automatically replicated with the channels when they are published. 

Follow this page to learn the manuals steps required to publish these configurations separately.

This basically comes down to manually publishing:

1. ContextHub Store and UI modules configurations
1. Personalization audiences
1. Personalization activities

## Steps for Replicating Data Triggers to Publish Server {#replicating-data-triggers-publish}

Follow the steps below to replicate the data triggers to publish server:

### Replicating ContextHub Configurations {#replicating-contexthub-configurations}

1. Navigate to **Tools** > **Deployment** > **Distribution** > **Publish Agent**
http://localhost:4502/libs/granite/distribution/content/distribution-agent.html?agentName=publish
1. Click the Test Connection button to validate the author can properly communicate with the publish instance
1. If the test fails, you need to fix the replication agent config between author and publish
1. Ensure the endpoint URL is also pointing to the publish server URL in Distribution Agent
1. Edit > Importer Endpoints 
1. Click the Distribute tab
1. Select Add tree radio button
1. In the path browser, select the configuration path for your project (i.e. /conf/screens/settings/cloudsettings/configuration)
1. Click Submit

### Replicating the Audiences {#replicating-audiences}

1. Navigate to Tools > Personalization > Audiences
http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/audiences.html
1. Drill down into your project folder (i.e. /conf/screens/)
1. Select all audiences/segments in the UI
1. Click Manage Publication
1. Click Next
1. Click Publish

### Replicating the Activities  {#replicating-activities}

1. Navigate to Tools > Personalization > Activities
http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html
1. Drill down into your project folder (i.e. /content/campaigns/screens/…)
1. Select all activities in the UI
1. Click Manage Publication
1. Click Next
1. Click Publish

> [!Note] 
>Replicating ContextHub configurations and audiences is done during the project setup, while replicating activities and will be required every time targeting is changed inside a channel.

#### Result {#result}

If replication is successful, you should view the following structure on the publish instance (or similar for your project):

`/conf/screens/settings/cloudsettings/configuration/…`
`/conf/screens/settings/wcm/segments/…`
`/content/campaigns/screens/…`