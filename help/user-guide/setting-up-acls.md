---
title: Setting up ACLs
description: Learn how to segregate projects using Access Control Lists (ACLs) so that each individual or team handles their own project.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: b40bcc9f-307c-422c-8abb-5c15965772d4
---
# Setting up Access Control Lists (ACLs) {#setting-up-acls}

The following section explains how to segregate projects using Access Control Lists (ACLs) so that each individual or team handles their own project.

As an AEM administrator, you want to ensure that team members of a project do not interfere with other projects. Each user is assigned specific roles as per project requirements.

## Setting up Permissions {#setting-up-permissions}

The following steps summarize the procedure for setting up ACLs for a project:

1. Login to AEM and navigate to **Tools** > **Security**.

   ![screen_shot_2018-02-16at10156pm](assets/screen_shot_2018-02-16at10156pm.png)

1. Click **Groups** and enter an ID (for example, Acme).

   Alternatively, use this link, `http://localhost:4502/libs/granite/security/content/groupadmin.html`.

   Next, click **Save**.

   ![screen_shot_2018-02-16at12648pm](assets/screen_shot_2018-02-16at12648pm.png)

1. Click **Contributors** from the list and double-click it.

   ![screen_shot_2018-02-18at33938pm](assets/screen_shot_2018-02-18at33938pm.png)

1. Add the **Acme** (project that you created) to **Add Members to the Group**. Click **Save**.

   ![screen_shot_2018-02-18at35630pm](assets/screen_shot_2018-02-18at35630pm.png)

   >[!NOTE]
   >
   >If you want project team members to register players (which involves creating a user for every player) find the group user-administrators and add the ACME group to user-administrators

1. Add all the users who are working on the **Acme** Project to the **Acme** group.

   ![screen_shot_2018-02-18at41320pm](assets/screen_shot_2018-02-18at41320pm.png)

1. Set up the permissions for the group **Acme** using this `(http://localhost:4502/useradmin)`.

   Click the group **Acme** and click the **permissions**.

   ![screen_shot_2018-02-18at41534pm](assets/screen_shot_2018-02-18at41534pm.png)

### Permissions {#permissions}

The following table summarizes the path with the permissions at the project level:

| **Path** |**Permission** |**Description** |
|---|---|---|
| `/apps/<project>` |READ |Provide access to project files, if applicable. |
| `/content/dam/<project>` |ALL |Provide access to store the project assets such as images or video in DAM. |
| `/content/screens/<project>` |ALL |Removes access to all other projects under /content/screens. |
| `/content/screens/svc` |READ |Provide access to the registration service. |
| `/libs/screens` |READ |Provide access to DCC. |
| `/var/contentsync/content/screens/` |ALL |Help you update offline content for the project. |

>[!NOTE]
>
>Sometimes, you can separate author functions (such as managing assets and creating channels) from admin functions (such as registering players). In such a scenario, create two groups and add the author's group to contributors and the admin group to both contributors and user-administrators.

### Creating Groups {#creating-groups}

Creating a project should also create default user groups with a basic set of permissions assigned. Extend the permissions to the typical roles defined in AEM Screens.

For example, you can create the following project-specific groups:

* Screens Project Administrators
* Screens Project Operators (register players, and manage locations and devices)
* Screens Project Users (work with channels, schedules, and channel assignments)

The following table summarizes the groups with description and permissions for an AEM Screens project:

<table>
 <tbody>
  <tr>
   <td><strong>Group name</strong></td>
   <td><strong>Description</strong></td>
   <td><strong>Permissions</strong></td>
  </tr>
  <tr>
   <td>Screens Admins<br /> <em><code>screens-admins</code></em></td>
   <td>Admin level access for AEM Screens capabilities</td>
   <td>
    <ul>
     <li>Member Of Contributors</li>
     <li>Member OF user-administrators</li>
     <li>ALL /content/screens</li>
     <li>ALL /content/dam</li>
     <li>ALL /content/experience-fragments</li>
     <li>ALL /etc/design/screens</li>
    </ul> </td>
  </tr>
  <tr>
   <td>Screens Users<br /> <em><code>screens-users</code></em></td>
   <td>Create and update channels and schedules and assign to locations in AEM Screens</td>
   <td>
    <ul>
     <li>Member Of Contributors</li>
     <li><code>&lt;project&gt; /content/screens</code></li>
     <li><code>&lt;project&gt; /content/dam</code></li>
     <li><code>&lt;project&gt; /content/experience-fragments</code></li>
    </ul> </td>
  </tr>
  <tr>
   <td>Screens Operators<br /> <em><code>screens-operators</code></em></td>
   <td>Create and update location structure and register players in AEM Screens</td>
   <td>
    <ul>
     <li>Member Of Contributors</li>
     <li><code>jcr:all /home/users/screens</code></li>
     <li><code>jcr:all /home/groups/screens</code></li>
     <li><code>&lt;project&gt; /content/screens</code></li>
    </ul> </td>
  </tr>
  <tr>
   <td>Screens Players<br /> <em><code>screens-&lt;project&gt;-devices</code></em></td>
   <td>All players and all players/devices are members of the contributors automatically.</td>
   <td><p> Member of Contributors</p> </td>
  </tr>
 </tbody>
</table>
