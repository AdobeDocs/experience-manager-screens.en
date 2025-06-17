---
title: Device Registration
description: Learn about the device registration process in an AEM Screens project.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: administering
docset: aem65
feature: Administering Screens, Device Registration
role: Admin
level: Intermediate
exl-id: b2d3a2cd-263f-4142-80da-29ce54cbf391
---
# Device Registration {#device-registration}

The following page describes the device registration process in an AEM Screens project.

## Registering a Device {#registering-a-device}

The device registration process is done on two separate machines:

* The actual device to be registered, for example your Signage Display
* The AEM server that is used to register your device

>[!NOTE]
>
>After you download the latest Windows Player (*.exe*), from the [AEM 6.4 Player Downloads](https://download.macromedia.com/screens/) page, follow the steps on the player to complete the ad-hoc installation:
>
>1. Long-press on the top-left corner to open the admin panel.
>1. Navigate to **Configuration** from the left action menu and enter the location address of the AEM instance in **Server** and click **Save**.
>1. Click the **Registration** link from the left action menu and the steps below to complete the device registration process.
>

![screen_shot_2018-11-26at12118pm](assets/screen_shot_2018-11-26at12118pm.png)

1. On your device, start the AEM Screens Player. The registration UI is shown.

   ![screen_shot_2018-11-26at104230am](assets/screen_shot_2018-11-26at104230am.png)

1. In AEM, navigate to the **Devices** folder of your project.

   >[!NOTE]
   >
   >To get more information on creating a project for Screens in the AEM dashboard, see [Create and Manage Screens Project](creating-a-screens-project.md).

1. Click the **Device Manager** button in the action bar.

   ![screen_shot_2018-11-26at104702am](assets/screen_shot_2018-11-26at104702am.png)

1. Click the **Device Registration** button on the top right.

   ![screen_shot_2018-11-26at104815am](assets/screen_shot_2018-11-26at104815am.png)

1. Click the required device (same as step 1) and click **Register Device**.

   ![screen_shot_2018-11-26at105112am](assets/screen_shot_2018-11-26at105112am.png)

1. In AEM, wait for the device to send its registration code.

   ![screen_shot_2018-11-26at105150am](assets/screen_shot_2018-11-26at105150am.png)

1. In your device, check the **Registration Code**.

   ![screen_shot_2018-11-26at105227am](assets/screen_shot_2018-11-26at105227am.png)

1. If the **Registration Code** is the same on both machines, click the **Validate** button in AEM, as shown in step (6).
1. Set the desired name for the device, and click **Register**.

   ![screen_shot_2018-11-26at105357am](assets/screen_shot_2018-11-26at105357am.png)

1. Click **Finish** to complete the registration process.

   ![screen_shot_2018-11-26at105456am](assets/screen_shot_2018-11-26at105456am.png)

   >[!NOTE]
   >
   >The **Register New** lets you register a new device.
   >
   >**Assign Display** lets you directly add the device to a display.

   If you click **Finish**, assign the device to a display.

   ![screen_shot_2018-11-26at105740am](assets/screen_shot_2018-11-26at105740am.png)

   >[!NOTE]
   >
   >To learn more about creating and managing a display for your Screens project, see [Creating and Managing Displays](managing-displays.md).

### Assigning Device to a Display {#assigning-device-to-a-display}

If you have not assigned the device to a display, follow the steps below to assign your device to a display in your AEM Screens project:

1. Click the device and click **Assign Device** from the action bar.

   ![screen_shot_2018-11-26at111026am](assets/screen_shot_2018-11-26at111026am.png)

1. Click the path of the display in **Display/Device Config Path**.

   ![screen_shot_2018-11-26at111252am](assets/screen_shot_2018-11-26at111252am.png)

1. Click **Assign** when you click the path.

   ![screen_shot_2018-11-26at111722am](assets/screen_shot_2018-11-26at111722am.png)

1. Click **Finish** once the device is assigned successfully, as shown in the figure below.

   ![screen_shot_2018-11-26at112041am](assets/screen_shot_2018-11-26at112041am.png)

   Also, you can view the display dashboard by selecting **Finish**.

   ![screen_shot_2018-11-26at112154am](assets/screen_shot_2018-11-26at112154am.png)

## Searching a Device from the Device Manager {#search-device}

When you have registered devices to your player, you can view all the devices from the Device Manager UI.

1. Navigate to the Device Manager UI from your AEM Screens project, for instance, **DemoScreens** > **Devices**. 

1. Click the **Devices** folder and click **Device Manager** from the action bar.

    ![image](/help/user-guide/assets/device-manager/device-manager-1.png)

1. The list of registered devices displays.

1. If you have a long list of registered devices, you can now search using the search icon from the action bar 

   ![image](/help/user-guide/assets/device-manager/device-manager-2.png)

   Or,

   Select `/` (forward slash) to invoke the search functionality.

     ![image](/help/user-guide/assets/device-manager/device-manager-3.png)


### Limitations on Search Functionality {#limitations}

* The user is able to search any word existing in the *device ID* or *device Name*. 

   >[!NOTE]
   >It is recommended that you create the device names in multiple words such as *`Boston Store Lobby`* rather than one single *`BostonStoreLobby`*.

* If you created device names such as *`Boston Store Lobby`*, it searches for any word *`boston`*, *`store`*, or *`lobby`*. However, if the device name is *`BostonStoreLobby`*, then searching for *`boston`* does not show any results.

* Wild card, `*` is supported for search. In case you want to find all the devices with names starting with *`boston`*, you can use *`boston`**.

* If the device name is *`BostonStoreLobby`* and searching for *`boston`* does not return the result, then using *`boston`** in your search criteria returns the result.

## Limitations on Device Registration {#limitations-on-device-registration}

System-wide user password restrictions might cause failure in the device registration. The device registration uses a randomly generated password to create the device user.

If the *AuthorizableActionProvider* configuration restricts the password, creating the device user might fail.

>[!NOTE]
>
>The current generated random password is composed of 36 ASCII characters, ranging 33 through 122 (includes almost all special characters).

```java
25.09.2016 16:54:03.140 *ERROR* [59.100.121.82 [1474844043109] POST /content/screens/svc/registration HTTP/1.1] com.adobe.cq.screens.device.registration.impl.RegistrationServlet Error during device registration
javax.jcr.nodetype.ConstraintViolationException: Password violates password constraint (^(?=.*\d).{7,9}$).
        at org.apache.jackrabbit.oak.spi.security.user.action.PasswordValidationAction.validatePassword(PasswordValidationAction.java:105)
        at org.apache.jackrabbit.oak.spi.security.user.action.PasswordValidationAction.onPasswordChange(PasswordValidationAction.java:76)
        at org.apache.jackrabbit.oak.security.user.UserManagerImpl.onPasswordChange(UserManagerImpl.java:308)
```

### Other Resources {#additional-resources}

To learn more about AEM Screens Player, see [AEM Screens Player](working-with-screens-player.md).
