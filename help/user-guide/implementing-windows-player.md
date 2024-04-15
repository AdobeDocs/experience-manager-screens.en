---
title: Implementing Windows 10 Player
description: Learn about configuring AEM Screens Windows 10 player.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
content-type: reference
docset: aem65
feature: Administering Screens, Windows Player
role: Admin
level: Intermediate
exl-id: 50b6d9ba-e672-4f4d-a9a8-fb8387685057
---
# Implementing Windows 10 Player {#implementing-windows-player}

This section describes configuring AEM Screens Windows 10 player. It provides information of the configuration file and the options available and recommendations as to which settings to use for development and testing.

## Installing Windows Player {#installing-windows-player}

To implement Windows Player for AEM Screens, install Windows Player for AEM Screens.

Visit the [**AEM 6.5 Player Downloads**](https://download.macromedia.com/screens/) page.

>[!NOTE]
>There is no window mode in Windows player. It is always full screen mode.

### Setting up Environment for AEM Screens 6.5.5 Service Pack {#fp-environment-setup}

>[!NOTE]
>Set up an environment for Windows player if you are using AEM Screens 6.5.5 Service Pack.

Set the **SameSite attribute for the login-token cookies** from **Lax** to **None** from **Adobe Experience Manager Web Console
Configuration** on all AEM author and publish instances.

Follow the steps below:

1. Navigate to **Adobe Experience Manager Web Console
Configuration** using `http://localhost:4502/system/console/configMgr`.

1. Search for *Adobe Granite Token Authentication Handler*.

1. Set the **SameSite attribute for the login-token cookies** from **Lax** to **None**.
   ![image](/help/user-guide/assets/granite-updates.png)

1. Select **Save**.

### Ad-Hoc method {#ad-hoc-method}

The Ad-Hoc method lets you install the latest Windows Player (*.exe*). Visit [**AEM 6.5 Player Downloads**](https://download.macromedia.com/screens/) page.

After you download the application, follow the steps on the player to complete the ad-hoc installation:

1. Long-press on the top-left corner to open the admin panel.
1. Navigate to **Configuration** from the left action menu and enter the location (address) of the AEM instance you wish to connect to and select **Save**.
1. Navigate to the **Device** **Registration** link from the left action menu so you can check the status of the device registration process.

>[!NOTE]
>
>If the **State** is **REGISTERED**, notice that the **Device id** field is populated.
>
>If the **State** is **UNREGISTERED**, you can use the **Token** to register the device.

## Naming Windows Player {#name-windows}

You can assign a user-friendly device name to your Windows player, thus sending the assigned device name to Adobe Experience Manager (AEM). This capability not only lets you name your Windows player but also allows to you to easily assign appropriate content.

>[!NOTE]
>You can choose the Player name only before registration. After the Player is registered, the Player name cannot be changed anymore.

Follow the steps below to configure the name in Windows player:

1. Select **start** > **run**.
1. Enter `system.cpl`.
1. Use the computer name tab to set the computer's hostname.

## Changing the Default Options in Windows Installer {#changing-default-options}

Follow this section so you can learn how to change the default options in Windows Installer and the list of available customizations.

## Installation using CLI (PowerShell) {#install-powershell}

 1. Create a custom location **dedicated** for Screens Player, for example: 
   `C:\Users\User\screens-player`)
 1. Install 
    `aem-screens-player-electron-xxx-signed.exe /S /D=C:\Users\User\screens-player`
 1. Open 
    `Start-Process C:\Users\User\screens-player\AEMScreensPlayer.exe`

**Example**

```shell
C:\Users\User\Downloads> mkdir screens-player

C:\Users\User\Downloads> .\aem-screens-player-electron-xxx-signed.exe /S /D=C:\Users\User\Downloads\screens-player

C:\Users\User\Downloads> Start-Process C:\Users\User\Downloads\screens-player\AEMScreensPlayer.exe
```

## Bulk Registration of Windows Player {#bulk-registration}

When implementing the windows player, you need not manually configure every player. Instead, you can update the configuration JSON file after it is tested and is ready for deployment.

The configuration makes sure that all players ping the same server provided in the configuration file. Manually register each player.

Follow the steps below to configure the Windows 10 Player:

1. Install Windows Player.
1. Find the configuration file under ***%appdata%\com.adobe.aem.screens.player\config.json***.
1. Update the configuration JSON using the information below and then copy the same folder to all the systems where the player resides.

### Policy Attributes {#policy-attributes}

The following table summarizes the policy attributes with an example policy JSON for reference:


| **Policy Name** |**Purpose** |
|---|---|
| server |The URL to the Adobe Experience Manager (AEM) server. |
| registrationKey |Used for bulk registration of devices using pre-shared key. |
| resolution |The resolution of the device. |
| rebootSchedule |The schedule to reboot the player.|
| enableAdminUI |Enable the Admin UI to configure the device on site. Set to false once it is fully configured and in production. |
| enableOSD |Enable the channel switcher UI for users to switch channels on device. Consider setting to false, once it is fully configured and in production. |
| enableActivityUI |Enable so you can show progress of activities such as download and sync. Enable for troubleshooting and disable once it is fully configured and in production. |
| cloudMode |Set to true if you want the Windows player to connect to Screens as a Cloud Service. Set to false to connect to AMS or on-prem AEM. |
| cloudToken |Registration token to register against Screens as a Cloud Service. |

#### Example policy JSON file {#example-policy-json-file}

```
{
    "server": "https://localhost:4502",
    "resolution": "auto",
    "rebootSchedule": "at 4:00 am",
    "enableAdminUI": false,
    "enableOSD": false,
    "enableActivityUI": false
}
```

## Enabling Kiosk Mode {#enabling-kiosk-mode}

When you are deploying the Windows player, it is important to enable a Kiosk mode so that other applications or the taskbar do not appear on the Windows desktop.

>[!CAUTION]
>
>Adobe recommends a device management solution to enable Kiosk for Windows. Follow the steps below, if you do not have a device management solution to enable Kiosk mode. This method uses the Shell Launcher feature available in Windows 10 enterprise and Edu. Any other Microsoft-recommended means for non-UWP apps can also be applied to enable Kiosk especially on other editions of Windows.

Follow the steps below to enable Kiosk mode:

>[!NOTE]
>
>Before you follow the steps below, ensure that you use Windows 10 Enterprise or Education.

1. Enable Shell Launcher.

   See ***Configure Shell Launcher*** in **[Shell Launcher](https://learn.microsoft.com/en-us/windows/iot/iot-enterprise/customize/shell-launcher)** page by Microsoft&reg; Windows support for additional information.

1. Create a non-administrative user (if you already do not have one) to be used for Kiosk. This can be a local or domain user.
1. Install the windows player for that Kiosk user from [AEM Screens Player Downloads](https://download.macromedia.com/screens/) page.
1. See [Use Shell Launcher to create a Windows 10 kiosk](https://learn.microsoft.com/en-us/windows/configuration/assigned-access/shell-launcher/?tabs=intune) to modify your PowerShell script for more information.

   Modify the PowerShell script so you can replace the username with the one you created. Ensure that the path to the application executable is correct. This sets the custom shell as the windows player application for the kiosk user and set the default as explorer.exe for other users.

1. Run the PowerShell script as an administrator.
1. Reboot and login as the Kiosk user and the player application should start right up.

### Troubleshooting {#troubleshooting}

If you get a black screen after you log in as the Kiosk user, it means that you may have incorrectly specified the path to the windows player executable. Log back in as the administrator and verify and rerun the script.

The default installation path for Windows player is:

***C:\Users\<your user>\AppData\Local\Programs\@aem-screensscreens-player-electron\AEM Screens Player.exe***

The sample script in the links enables and disables the custom shell. Therefore, split the script into two and enable/disable the below applicable lines:

>[!NOTE]
>
>In some windows environments, the PowerShell scripts maybe restricted by policy (especially unsigned scripts). To run your script, temporarily disable and reenable this restriction to run the script. Open a PowerShell window and use these commands.
>
>*`set-executionpolicy unrestricted`* - to temporarily remove restrictions.
>
>*`set-executionpolicy restricted`* - to re-enable restriction after running the script.

```
# Remove the new custom shells.

$ShellLauncherClass.RemoveCustomShell($Admins_SID)

$ShellLauncherClass.RemoveCustomShell($Cashier_SID)
```

### Using the Screens Remote Control {#using-remote-control}

AEM Screens provides Remote Control functionality. Learn more about this feature here: [Screens Remote Control](implementing-remote-control.md)