
Source: **[https://vcb-s.com/archives/7594](https://vcb-s.com/archives/7594)**

---

[mpv](https://mpv.io/) is a fork of the well-known open source project MPlayer, widely praised for its support for the latest hardware and software platforms, video standards, and various high-definition options, and is currently the best choice for high-definition players on non-Windows platforms. we introduced earlier is an mpv-based player front-end.

Since mpv itself does not have a graphical interface, various settings need to be completed by manually writing configuration files, which discourages many ordinary users who are not familiar with command lines. The main purpose of this article is to provide a start-up guide for Windows and macOS users of mpv players, and teach you how to use mpv step by step.

---

**Set file type associations**

File type association under Windows should have been done by the installation script. Under macOS, take an MKV file as an example, right-click on any MKV file - Show Info - Open With - Change All, and then select mpv.  
Simple player control interface

mpv provides some simple controls on the playback interface. Moving the mouse over the video screen displays a floating control bar at the bottom of the interface.

The three buttons on the far left at the bottom are play/pause, jump to chapters before and after, respectively. The buttons to the right of the progress bar are to switch audio tracks, switch subtitles, adjust volume and display in full screen/window. Left-click the audio track and subtitle button to switch the audio track or subtitle directly, and Shift + left button can display the currently loaded audio track or subtitle list.

---

**Common shortcut keys**

→ go forward 5 seconds  
← back 5 seconds  
↑ go forward 1 minute  
↓ go back 1 minute  
PageUpJump to the next chapter  
PageDownJump to previous chapter  
Space play / Pause  
9 lower the volume  
0 Increase the volume  
j Toggle subtitles  
# switch track  
f Toggle full screen/window display  
s screenshot

In addition, shortcut keys iIt can display the media information of the currently playing file and related data of decoding and rendering (as shown in the figure below). use Shift + iyou can keep the information displayed or clear, click 1 and 2The first and second pages of information can be displayed separately.

---

**Create configuration file**

Although the default settings of mpv are enough to play most videos normally, in order to achieve better results and meet personal usage habits, we still need some configuration.

Open Notepad (Notepad) or any plain text editor you like under Windows, create a new blank document, write the configuration command (see below), and create a new file named in the decompression directory of mpv just now. portable_confignew folder, e.g. C:\mpv\portable_config, name the configuration file as mpv.confSave it in this folder (note that if you use Notepad, you need to select "All files (_._)" for "Save as type" when saving the file, otherwise the file name will be added .txtextension, becomes mpv.conf.txt）。

Under macOS, first open the location where the configuration file is to be saved by opening the Go to Folder under the Go menu in the top bar of the Finder, and then entering:

~/.config/mpv

(Because this folder is hidden by default and cannot be opened directly), then open the TextEdit application that comes with macOS, create a new document, and select Make Plain Text in the "Format" menu. , after writing the configuration command (see below), save this file in the mpv folder you just opened with the file name mpv.conf。  
Recommended configuration commands to add

The default render settings for mpv are very conservative. If your graphics card performance is not too bad (integrated graphics cards are generally sufficient in recent years), it is recommended to enable a set of preset high-quality rendering settings by mpv.confWrite this line in:

profile=gpu-hq

Note that using high-quality rendering settings can significantly reduce notebook battery life, especially on recent high-resolution screens (such as "retina display" MacBooks).

mpv does not color manage video by default. Even if you have not calibrated the screen with a color calibrator, for a screen whose native color gamut is close to a standard color gamut (such as sRGB or DCI-P3 D65), turning on color management can still get more accurate colors, so , I recommend always turning color management on:

icc-profile-auto

Set to render the subtitles to the video source resolution and scale with the video and perform color management, which can ensure that the resolution of the subtitles is always consistent with the picture (avoid the situation of "blurred subtitles HD"), and ensure the "screen words" in the subtitles The color is the same as the picture:

blend-subtitles=video

If you have a mid-to-high-end discrete graphics card and want to further improve the picture stretching quality, you can change the picture stretching algorithm to EWA Lanczos (that is, the so-called Jinc in madVR):

scale=ewa_lanczossharp

In many cases, our monitor refresh rate is not an integral multiple of the source frame rate (for example, the monitor refresh rate is usually 60 Hz and the animation is usually 23.976 fps). The presentation time is uneven and causes a sense of stuttering (commonly known as 3:2 pull down judder). Therefore, it is recommended to enable interpolation to eliminate this problem (this feature is very similar to smooth motion in madVR):

video-sync=display-resample  
interpolation  
tscale=oversample

These are some options that I think are universal. There are many other places that can be customized. For details, please refer to the official documentation for the explanation of hundreds of settings. In addition, mpv provides third-party user script support, which can achieve more functions (such as setting profiles to perform different processing for different source types), and third-party user shaders to achieve more picture processing (such as NNEDI3, RAVU, etc. Wait).

Compared with using the mouse to click and click in the graphical interface, the way of handwriting the configuration file is not in line with the habits of ordinary users, but "once you accept this setting", you will gradually realize the convenience and flexibility of the command line.

For the configuration method of mpv, please refer to:

cczzhh's post on the VCB-Studio forum with detailed notes and instructions

mpv developer hassn's personal mpv configuration

Personal mpv configuration by mpv developer Argon-  
Replenish

---

**Setting up a dual-graphics laptop**

If you are using a Windows laptop with an integrated graphics card + NVIDIA discrete graphics card, mpv will only call the integrated graphics card for rendering calculations by default, and the performance is limited. If you want to take advantage of high performance discrete graphics, you need to go to NVIDIA Control Panel - 3D Settings - Manage 3D Settings - Program Settings, add mpv.exe, and change the preferred graphics processor to "High-performance NVIDIA processor", and change the power management mode to "Adaptive" as above.

If you're using a dual-graphics MacBook Pro, you can force mpv to use the discrete graphics by adding this line to the config file:

cocoa-force-dedicated-gpu=yes  
IINA uses the mpv profile

IINA can directly read the mpv configuration file to share the settings, just check "Use configuration directory" at the bottom of the Preferences - Advanced tab, the default ~/.config/mpvIt is the directory where the default configuration file of mpv is located. It is worth noting that a small number of mpv settings have no effect on IINA, see here .

You can also add mpv settings directly under the advanced tab of IINA, just add each line in the settings mentioned above =The content on the left and right sides can be filled in "Options" and "Values" respectively.

---

**FAQ**

Q: Well, cross-platform, what about Linux?

A: If you are a daily Linux user, you should be familiar with the command line and configuration files. You must already know how to do it through the above instructions.

Q: Which picture quality is better, mpv or madVR?

A: mpv is a full-featured standalone player, madVR is just a renderer and needs to work with other players (such as MPC-BE). There are some differences in how the two are designed and implemented when it comes to video rendering, but when using similar settings, the difference in image quality is minimal.

Q: Is there a lazy bag?

A: No.