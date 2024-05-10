---
title: Configuring Author and Publish instances in AEM Screens
description: Learn how to configure an Author instance and a Publish instance for AEM Screens.
exl-id: 5aef5f35-d946-4bf8-a2a8-c3ed532b7eef
---

# Configuring Author and Publish instances in AEM Screens {#configuring-author-and-publish-in-aem-screens}

This page highlights the following topics:

* **Configuring Author and Publish instances**
* **Setting Up Publish Topology**
* **Managing Publication: Delivering Content Updates from Author to Publish to Device**

## Prerequisites {#prerequisites}

Before getting started with Author and Publish Servers, you should have prior knowledge of:

* **AEM Topology**
* **Creating and Managing AEM Screens Project**
* **Device Registration Process**

>[!NOTE]
>
>This AEM Screens functionality is only available if you have installed AEM 6.4 Screens Feature Pack 2. To get access to this Feature Pack, contact Adobe Support and request access. After you have permission, you can download it from Package Share.

>[!IMPORTANT]
>
>If you want to use more than one Publish instance with Dispatcher, update the Dispatcher. See [Enabling Sticky Sessions](dispatcher-configurations-aem-screens.md#enable-sticky-session).

## Configuring Author and Publish instances {#configuring-author-and-publish-instances}

>[!NOTE]
>
>To learn more about the Author and Publish architectural overview and how the content is authored on an AEM Author instance and then forward-replicated to multiple Publish instances, see [Author and Publish Architectural Overview](author-publish-architecture-overview.md).

The following section explains how to set up replication agents on the Author and Publish topology.

You can set up a simple example, where you host an Author and two Publish instances:

* Author > localhost:4502
* Publish 1 (pub1) > localhost:4503
* Publish 2 (pub2) > localhost:4504

## Setting up Replication Agents on Author {#setting-replication-agents}

To create replication agents, learn how to create a standard replication agent.

There are three replication agents that are needed for Screens:

1. **Default Replication Agent ***(specified as*** Standard Replication Agent**)
1. **Screens Replication Agent**
1. **Reverse Replication Agent**

### Step 1: Creating a Default Replication Agent {#step-creating-a-default-replication-agent}

Follow the steps below to create a default replication agent:

1. Navigate to your AEM instance > hammer icon > **Operations** > **Configuration**.

   ![screen_shot_2019-02-25at24621pm](assets/screen_shot_2019-02-25at24621pm.png)

1. Click the **Replication** from the left navigation tree.

   ![screen_shot_2019-02-25at24715pm](assets/screen_shot_2019-02-25at24715pm.png)

1. Click the **Agents on Author** from the **Replication** folder and click **New** to create a new standard replication agent.

   ![screen_shot_2019-02-25at25400pm](assets/screen_shot_2019-02-25at25400pm.png)

1. Enter the **Title** and **Name** so you can create the replication agent, then click **Create**.

   ![screen_shot_2019-02-25at25737pm](assets/screen_shot_2019-02-25at25737pm.png)

1. Right-click the replication agent and click **Open** to edit the settings.

   ![screen_shot_2019-02-25at30018pm](assets/screen_shot_2019-02-25at30018pm.png)

1. Click **Edit**.

1. In the **Agent Settings** dialog box, enter the details.

   >[!NOTE]
   >
   >The user must check **Enabled** to enable the replication agent. Check this option on Default, Screens, and Reverse Replication Agents.

   ![screen_shot_2019-02-25at30134pm](assets/screen_shot_2019-02-25at30134pm.png)

1. Navigate to the **Transport** tab and enter the **URI**, **User**, and **Password**.

   ![screen_shot_2019-03-04at34955pm](assets/screen_shot_2019-03-04at34955pm.png)

   >[!NOTE]
   >
   >You can also copy and rename an existing default replication agent.


#### Creating Standard Replication Agents {#creating-standard-replication-agents}

1. Create a standard replication agent for pub1 (an out-of-the-box default agent should already be configured). For example, *`https://<hostname>:4503/bin/receive?sling:authRequestLogin=1`*
1. Create a standard replication agent for pub2. You can copy s replication agent for pub1 and update the transport to be used for pub2 by changing the port in the transport configuration. For example, *`https://<hostname>:4504/bin/receive?sling:authRequestLogin=1`*.

#### Creating Screens Replication Agents {#creating-screens-replication-agents}

1. Create an AEM Screens replication agent for pub1. Out-of-the-box, there is one named Screens replication agent that points to port 4503. Enable it.
1. Create an AEM Screens replication agent for pub2. Copy the Screens replication agent for pub1 and change the port to point to 4504 for pub2.

   >[!NOTE]
   >To learn how to configure Screens replication agents, see [Configuring Screens Replication Agent](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/configure-screens-replication).

#### Creating Screens Reverse Replication Agents {#creating-screens-reverse-replication-agents}

1. Create a reverse replication agent for pub1.
1. Create a reverse replication agent for pub2. You can copy the reverse replication agent for pub1 and update the transport to be used for pub2 by changing the port in the transport configuration.

## Setting up Publish Topology {#setting-up-publish-topology}

### Step 1: Configure Apache Sling Oak-Based Discovery {#step-configure-apache-sling-oak-based-discovery}

Set up Apache Sling Oak-Based Discovery for all Publish instances in the topology

For each Publish instance:

1. Navigate to `https://<host>:<port>/system/console/configMgr`
1. Click **Apache Sling Oak-Based Discovery Service** Configuration.
1. Update Topology connector URLs: add URLs of all partaking Publish instances that are:
   * `https://publish:4503/libs/sling/topology/connector`
   * `https://publish:4504/libs/sling/topology/connector`
1. **Topology connector `Whitelist` List**: Adapt to IPs or subnets covering all Publish instances. Ensure you `whitelist` the IP/hostname of all Publish instances without the port number.

1. Enable **Auto-Stop Local-Loops**

The configuration should be identical for each Publish instance and the auto-stop Local-loop prevents an infinite loop.

#### Step 2: Verify Publish Topology {#step-verify-publish-topology}

For any of the Publish instances, navigate to `https://:/system/console/topology`. You should see each Publish instance represented in the topology under **Outgoing topology connectors**.

#### Step 3: Setup ActiveMQ Artemis Cluster {#step-setup-activemq-artemis-cluster}

This step lets you create an encrypted password for the ActiveMQ Artemis cluster.
The cluster user and password of all Publish instances in the topology must be identical. The password of the ActiveMQ Artemis configuration must be encrypted. Because each instance has its own encryption key, it is necessary to use Crypto Support to create an encrypted password string. Then, the encrypted password can be used in the OSGi config for ActiveMQ.

On each Publish Instance:

1. In the OSGi Console, navigate to **MAIN** > **Crypto Support** (`https://<host>:<port>/system/console/crypto`).
1. Type in the desired plain text password (same for all instances) in **Plain Text**
1. Click **Protect**.
1. Copy the value **Protected Text** to a notepad or text editor. This value can be used in the OSGi config for ActiveMQ.

Because each Publish instance, by default, has unique crypto keys, perform this step on each pub instance and save the unique key for the next configuration.

>[!NOTE]
>
>The password should start and end with curly brackets. For example:
>`{1ec346330f1c26b5c48255084c3b7272a5e85260322edd59119828d1fa0a610e}`

#### Step 4: Activate ActiveMQ Artemis Cluster {#step-activate-activemq-artemis-cluster}

On each publishing instance:

1. Navigate to the OSGi Config manager `https://<host>:<port>/system/console/configMgr`
1. Click **Apache ActiveMQ Artemis JMS Provider** Configuration
1. Update the following:

   * ***Cluster Password***: use encrypted value from the previous step per respective instance
   * ***Topics***: `{name: 'commands', address: 'com.adobe.cq.screens.commands', maxConsumers: 50}`

#### Verify ActiveMQ Artemis Cluster {#verify-activemq-artemis-cluster}

Follow the steps below on each Publish instance:

1. Navigate to the OSGi Console > Main > ActiveMQ Artemis `https://localhost:4505/system/console/mq`.
1. Verify and check to view the ports of other instances under Cluster Information > Topology > nodes=2, members=2.
1. Send a Test Message (top of the screen under Broker Information)
1. Enter the following changes in fields:

    1. **Destination**: /com.adobe.cq.screens/devTestTopic
    1. **Text**: Hello World
    1. View the `error.log` of each instance so you can see that the message was sent and received across the cluster.

>[!NOTE]
>
>Navigating to OSGi Console may take a few seconds after saving the configuration in the preceding step. You can also check the error.log for more details.

As an example, the following image displays on successful configuration of ActiveMQ Artemis Server.

If you do not see the following configuration from */system/console/mq*, then navigate to */system/console/mq* and click **Restart** to restart the broker.

![image-2018-06-18-18-14-55-449](assets/image-2018-06-18-18-14-55-449.png)

#### Remove referrer header requirement {#remove-referrer-header-requirement}

Follow the steps in each Publish instance:

1. Navigate to the **OSGi Console** > **Configuration Manager**
1. Click **Apache Sling Referrer Filter**
1. Update config and **check Allow Empty**

### Configuring Author and Publish Instance {#configuring-author-and-publish-instance}

After you have set up the publishing topology, configure the Author and Publish instances to view the practical results of the implementation:

>[!NOTE]
>
>**Prerequisites**
>
>To get started with this example, create an AEM Screens project followed by creating a location, display, and channel in your project. Add content to your channel and assign the channel to a display.

#### Step 1: Starting an AEM Screens Player (device)

1. Launch a separate browser window.
1. Go to Screens player using the *web browser*, that is,`https://localhost:4502/content/mobileapps/cq-screens-player/firmware.html` or launch the AEM Screens app. When you open the device, notice the device's state as unregistered.

>[!NOTE]
>
>You can open an AEM Screens Player using the AEM Screens app you downloaded or using the Web browser.

#### Step 2: Registering a Device on Author {#step-registering-a-device-on-author}

1. Go to `https://localhost:4502/screens.html/content/screens/we-retail` or click your project and navigate to Devices > Device Manager.
1. Click **Register Device**.
1. Click **Device Registration**.
1. Click the device that you want to register, then click **Register Device**.
1. Verify the registration code, then click **Validate**.
1. Enter a title for your device, then click **Register**.

#### Step 3: Assigning the Device to Display {#step-assigning-the-device-to-display}

1. Click **Assign Display** from the dialog box from the preceding step.
1. Click the display path for your channel from the **Locations** folder.
1. Click **Assign**.
1. Click **Finish** to complete the process, and now the device is assigned.

Check your player and notice the content that you added in your channel.

#### Step 4: Publishing Device Configuration to Publish Instances {#step-publishing-device-configuration-to-publish-instances}

**Verifying the Device**

Follow the steps below to replicate the device user:

1. Navigate to the user admin page. For example, `https://localhost:4502/useradmin`.
1. Search for the **`screens-devices-master`** group.
1. Right-click the group and click **Activate**.

>[!CAUTION]
>
>Do not activate the author-publish-screens-service as it is a system user used by the Author Job.

You can also activate the device from the Device Management Console. Follow the steps below:

1. Navigate to your Screens project > **Devices**.
1. Click **Device Manager** from the action bar.
1. Click the device and click **Activate** from the action bar, as in shown in the figure below.

![screen_shot_2019-02-21at111036am](assets/screen_shot_2019-02-21at111036am.png)

>[!NOTE]
>
>Alternatively, after you have activated the device, you can also edit or update the server URL. From the action bar, click **Edit server URL**, as shown in the figure below. Your changes become propagated to the AEM Screens Player.

![screen_shot_2019-02-21at105527am](assets/screen_shot_2019-02-21at105527am.png)

### Publishing Check list {#publishing-check-list}

The following points summarize the Publishing Check list:

* *Screens Device User* - This information is stored as an AEM user and can be activated from **Tools** > **Security** > **Users**. The user is prefixed with "screens" with a long serialized string.

* *Project* - The AEM Screens project.
* *Location* - Location that the device is connected to.
* *Channels* - One or more channels that are being displayed at the location.
* *Schedule* - If using a schedule, ensure that this schedule is published.
* *Location, Schedules, and Channel Folder* - If the corresponding resources are inside a folder.

Follow the steps below to verify the authoring and publishing behavior:

1. Update some channel content on Author instance.
1. Perform **Manage Publication** to publish new changes to all Publish instances.
1. Press **Activate** to activate the device from **Device Manager**.
1. Select **Edit URL** from the Author instance URL to one of the Publishing instances URL.
1. Verify the updated channel content displays on the AEM Screens Player.
1. Repeat these steps using a different Publish instance.


#### Step 5: Pointing the Device to Publish Instance in the Admin Panel {#step-pointing-the-device-to-publish-instance-in-the-admin-panel}

1. View the admin UI from the Screens player, long press the top-left corner so you can open the Admin menu, on your touch-enabled AEM Screens Player, or by using a mouse.
1. Click the **Configuration** option from the side panel.
1. Change Author instance to Publish instance in **Server**.

View the changes in your AEM Screens Player.

Alternatively, you can also update/edit the server URL from the device management console using the following steps:

1. Navigate to your AEM Screens project and click the **Devices** folder.
1. Click **Device Manager** from the action bar.
1. Click the device, then from the action bar, click **Edit server URL**, as shown in the figure below. Your changes become propagated to the AEM Screens Player.

![screen_shot_2019-02-07at31028pm](assets/screen_shot_2019-02-07at31028pm.png)

The **Manage Publication** feature lets you deliver content updates from Author to Publish to device. You can publish/unpublish content for your entire AEM Screens project or only for one of your channels, location, device, application, or a schedule. To learn more about this feature, see [On-Demand Content Update](on-demand-content.md).

## Troubleshooting Tips {#troubleshoot-tips}

Follow the section below to get answers to frequently asked questions related to the Author/Publish setup.

### How to add a Redirect from https to http after initial registration and assignment? {#add-redirect}

**Solution**
Set Enable `Proxy/Load Balancer Connection in the Jetty configuration` to `true`.

### How to Update offline content and player download issues with assets outside `/content/dam/projects/<project>`? {#update-offline-content}

**Solution**
Give read permissions for bulk-offline-update-screens-service user and `screens-devices-master` group for all `/content/dam` or the specific assets that you want to use, if you want to be more restrictive.

### How to resolve Screens Replication Agent errors? {#replication-agent}

**Solution**
Make sure you have not checked Use for reverse replication option in the agent configuration. Screens replication agent cannot be used as a reverse replication agent and the scope of this feature is to forward device commands from Author to Publish.