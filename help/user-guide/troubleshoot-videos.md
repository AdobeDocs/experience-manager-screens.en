---
title: Video Playback Configuration and Troubleshooting
description: Learn how to debug and troubleshoot video playing in your channel for AEM Screens.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: troubleshoot
feature: Channels, Interactive
role: Developer
level: Intermediate
exl-id: dfdd58b6-689b-47ca-9459-9c205f1841eb
---
# Video Playback Configuration and Troubleshooting {#video-playback-configuration-and-troubleshooting}

When you upload a video to the DAM and add it your channel, you might encounter issues in which the video may not play in the AEM Screens player.

The following sections describe how to debug and troubleshoot video playing in your channel.

## DAM Renditions {#dam-renditions}

After you upload the video to the channel, AEM should start creating some renditions for it. You can view your videos under Assets.

To view the video:

1. Navigate to your video, for example `http://localhost:4502/assets.html/content/dam/we-retail/en/videos`.
1. Click the video and expand the top-left menu and click **Renditions**.

There should be different renditions (an MP4 or M4V).

If there is no rendition, make sure you have ffmpeg installed on the OS where AEM is running.

>[!CAUTION]
>
>If there is no rendition, make sure you have ffmpeg installed on the OS where AEM is running.
>
>Click [here](https://www.ffmpeg.org/download.html) to install ffmpeg.

## Video Assets {#video-assets}

If you do not see a source attribute under video, it could be that the video did not get trans-coded. If the video is transcoded properly, it appears in the dashboard, as shown in the following:

Check ffmpeg is installed and the video profiles.

![chlimage_1-2](assets/chlimage_1-2.png)

### Checking Video Profile {#checking-video-profile}

1. Navigate to the **Video Profile**, that is, `http://localhost:4502/etc/dam/video.html` and click **Upload Test Video**.

   ![chlimage_1-3](assets/chlimage_1-3.png)

1. Upload a test video and click **Ok** so you can begin the transcoding.

   If the transcoded video fails, expand the ffmpeg output to understand any errors in the console output of ffmpeg.

   ![chlimage_1-4](assets/chlimage_1-4.png)

   Also, if the video transcodes successfully can download the transcoded file.

   ![chlimage_1-5](assets/chlimage_1-5.png)

   >[!NOTE]
   >
   >Make sure you give sufficient time for the video to transcode (it should show the new tag instead of processing) before you add it to any channel.

### Checking Profile with a Video Component {#checking-profile-with-a-video-component}

Check the list of profiles from the page design if the video component is not configured properly.

1. Navigate to your channel and select the **Design** mode.

   ![chlimage_1-6](assets/chlimage_1-6.png)

1. Select the video and open the **Edit** dialog. Open the **Profiles** tab.

   >[!NOTE]
   >Select different profiles (at least "High Quality H.264" profile should be there).

### Checking the Video in the Web Player {#checking-the-video-in-the-web-player}

Use the **Web Player** `http://localhost:4502/content/mobileapps/cq-screens-player/firmware.html/content/screens/we-retail/locations/demo/flagship/single/device0` to validate playback in browsers (Chrome and Safari). Chrome is used on Android&trade; devices while Safari is the OS X and iOS browser.

If the video does not run on Safari, it does not run in the OS X and iOS players either. This is likely an encoding issue and the video must be re-encoded.

To use a DAM workflow to create FullHD renditions, do the following:

1. Navigate to the *workflow model admin* that is `http://localhost:4502/libs/cq/workflow/admin/console/content/models.html/etc/workflow/models`.
1. Select the **Screens Update Asset** model.
1. Select **Start Workflow** from the action bar.
1. From the **Run Workflow** dialog box, select your video asset in the **Payload**.
1. Select **Run**.

>[!NOTE]
>
>Allow some time to create the renditions, but after a few seconds/minutes (depends on video size), reload the web player on Safari.

#### Troubleshooting Autoplay Policy Flag {#troubleshooting-autoplay-policy-flag}

In case the AEM Screens player picks up the video but does not display, troubleshoot the Autoplay Policy flag.

Follow the steps below to troubleshoot Google's autoplay policy flag issue:

1. Navigate to ***chrome://flags/#autoplay-policy***
1. Change **Autoplay policy** from **Default** to **no user gesture is required**

1. Relaunch your web browser and update the player

>[!NOTE]
>
>To learn more about the best practices for good user experiences with the new autoplay policies in Chrome, see documentation for *Autoplay Policy Changes* at `https://developers.google.com/web/updates/2017/09/autoplay-policy-changes#webaudio`.

### Syncing Video across Multiple Players {#syncing-video-across-multiple-players}

To play videos synchronously across multiple devices, you should use the absolute strategy for the sequence the video is part of.

#### Requirements {#requirements}

* identical 2+ players
* ideally similar hardware
* identical network topology (players are connected to an NTP server that aligns their internal system clocks)

#### Setting up the absolute strategy {#setting-up-the-absolute-strategy}

The absolute strategy:

* Computes an anchor time (midnight of the current day).
* Computes the duration of the sequence (sum of duration of all its items).
* At any point in time, it computes which item should be currently played and the next item by solving sequence _remaining_time = (current_time - anchor_time) % sequence_duration.

Follow the steps below to set up an absolute strategy:

1. Navigate to your channel author and select the sequence component as shown in the figure below.
1. Open its configuration dialog.
1. Edit the **Strategy** and add absolute.

   ![chlimage_1-8](assets/chlimage_1-8.png)

   >[!NOTE]
   >The OS of the players must have the same clock.

**Aligning Clocks on OS X** Follow the steps below to align the clocks on OS X:

1. Open **Date & Time** preferences on each OS X box
1. Check **Set date and time automatically**
1. Paste value 0.pool.ntp.org, 1.pool.ntp.org, 2.pool.ntp.org, 3.pool.ntp.org, time.apple.com in the dropdown or simply run *sudo ntpdate -u -v 0.pool.ntp.org*
1. Start the 2+ players

It may take some time before the players start a new aligned sequence.
