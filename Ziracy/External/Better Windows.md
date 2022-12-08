-> ![Windows](https://icon-library.com/images/windows-10-logo-icon/windows-10-logo-icon-16.jpg) <-

Debloating Windows can free up wasted System resources and can improve performance in games and what not for low end PCs. But that doesn't mean high-end PCs won't get any benefits. Debloating will make Windows more Private since you remove and disable all the telemetry and what not that is constantly running sending data to Microsoft. Another benefit is less clutter and more customization, since debloating removes all Windows UWP apps (e.g Groove Music, Movie Editor, and etc.) this gives space to use way better alternatives and remove apps you never use. Overall, whether you have a low end or high end PC, its def worth debloating windows as it will make the experience using Windows smoother and better.

[TOC]
# Overview
There are two methods to make windows better first method being installing LTSC which is heavily debloated Windows ISO or Second Method which is running debloating scripts on existing Windows Install.

I would recommend first method as you will run into less issues afterwards but if you don't feel confident enough reinstalling your OS then second method is your best bet.

If you don't know how to use the certain tools listed (e.g NVCleaninstall, CTT Debloat, and etc.) there is a section called `"How to Use Tools"` section at the end.

#### Before We Start
!!!Danger Notice
	**Just in case, make a restore point of your windows before debloating. In case something happens to windows after a few weeks passes. Usually windows updates will try undo the debloats but will instead cause itself to break.**

## Special Guides
- [NVIDIA Control Panel without MS Store](https://rentry.co/gaydia)
- [Lenovo Vantage without MS Store](https://rentry.co/lenbian)


## How To Use the Tools
- [NVCleanInstall Guide](https://rentry.co/NVCleanInstall)
- [CTT Debloat Video](https://youtu.be/tPRv-ATUBe4)
!!!Note [CTT Debloat Guide](https://rentry.co/CitrusDebloater) previous guide
- [QuickBoost Guide](https://rentry.co/quickboost)
!!!Danger Notice
	Don't Run Uninstall Microsoft Store, if you did there is a Reinstall option in CTT

## For Pro Gamers
If you planning on gaming only on your device and nothing else then instead of LTSC, use AtlasOS a custom Windows ISO for gamers.
!!! Notice
	AtlasOS prioritizes performance/response over convenience and ease of use. There will be many useful features or stuff removed. Best not use this as a Daily Driver OS.
1. Install [AtlasOS](https://atlasos.net/)
2. Install & Run [NVCleanInstall](https://www.techpowerup.com/download/techpowerup-nvcleanstall/), allows you to install graphics driver without the bloat.
	1. For AMD use [Radeon Software Slimmer](https://github.com/GSDragoon/RadeonSoftwareSlimmer) or follow this guide [Stripping The AMD Driver](https://rentry.co/AMDDebloat)
!!! info
	That's all for this section, scroll down to the bottom for [Post Debloating](https://rentry.co/better-windows#post-debloating) and follow that if you want.

# First Method (Reinstalling Windows)
!!! note Note
	Recommended if you just bought a new PC/Laptop.
1. Install [Windows LTSC](https://supreme-gamers.com/t/windows-10-ltsc-the-best-windows-10-version-ever.845/), LTSC is windows but without the major bloatware.
!!! Info
	Download LTSC from [here](https://bobpony.com/downloads/) 
	Set the options like so for the dropdowns: 
	1. Windows (not Server or Beta) 
	2. 10 
	3. LTSC 2021 x64
2. Install & Run [NVCleanInstall](https://www.techpowerup.com/download/techpowerup-nvcleanstall/), allows you to install graphics driver without the bloat.
	1. For AMD use [Radeon Software Slimmer](https://github.com/GSDragoon/RadeonSoftwareSlimmer) or follow this guide [Stripping The AMD Driver]
!!!info
	**Optional:** Download & Run (as Admin) [Sophia Script](https://github.com/farag2/Sophia-Script-for-Windows) for LTSC, Sophia script is debloating script for removing last bit of bloatware
3. Download & Run (as Admin) [QuickBoost](https://github.com/SanGraphic/QuickBoost) and run the tweaks to improve performance.
!!! info
	That's all for this section, scroll down to the bottom for [Post Debloating](https://rentry.co/better-windows#post-debloating) and follow that if you want.

# Second Method (Pre-Installed Windows)
!!! note Note
	Recommended if you're using a existing PC/Laptop
1. Run (as Admin) [CTT Debloat](https://www.christitus.com/debloat-windows-10-2020/)
2. Install & Run [NVCleanInstall](https://www.techpowerup.com/download/techpowerup-nvcleanstall/), allows you to install graphics driver without the bloat.
	1. For AMD use [Radeon Software Slimmer](https://github.com/GSDragoon/RadeonSoftwareSlimmer) or follow this guide [Stripping The AMD Driver](https://rentry.co/AMDDebloat)
3. Download & Run (as Admin) [QuickBoost](https://github.com/SanGraphic/QuickBoost) and run the tweaks to improve performance.
4. Disable Windows Updates by downloading and running [Windows Update Blocker](https://www.sordum.org/9470/windows-update-blocker-v1-7/).
!!! info
	That's all for this section, scroll down to the bottom for [Post Debloating](https://rentry.co/better-windows#post-debloating) and follow that if you want.

# Post Debloating
This section is for after completed first or second method
\*FOSS means Free Open Source Software

1. Browser of your choice
!!! info
	I recommend either [FireFox Nightly](https://www.mozilla.org/en-US/firefox/channel/desktop/#:~:text=is%20shared.-,Nightly,-Get%20a%20sneak) or [Librewolf](https://librewolf.net/) a fork of Firefox that is FOSS (for chromium based use [Edge](https://www.microsoft.com/en-us/edge))
2. [FluentStore](https://github.com/yoshiask/FluentStore) (FOSS Microsoft Store Front End)
!!! info
	I recommend this if you installed LTSC or removed the MS Store during debloat
3. [ShareX](https://getsharex.com/) (FOSS lightweight screenshotting software that also can record screen)
!!! info
	I personally use and recommend [Flameshot](https://flameshot.org/) super lightweight and FOSS as well.
4. [Ditto Clipboard](https://ditto-cp.sourceforge.io/) (FOSS lightweight clipboard)
4. [Beauty Search](https://github.com/krlvm/BeautySearch) (FOSS Customize Windows Search)
4. [ImageGlass](https://imageglass.org) (FOSS Image Viewer with plugin and theme support)
5. [ModernFlyouts](https://github.com/ModernFlyouts-Community/ModernFlyouts) (FOSS modern flyouts for Windows)
6. [TaskbarX](https://github.com/ChrisAnd1998/TaskbarX/releases) (FOSS for customizing taskbar)
7. [EarTrumpet](https://github.com/File-New-Project/EarTrumpet) (FOSS Better Windows audio control) 
8. [Posy's Cursors](http://www.michieldb.nl/other/cursors/) (Revised and improved cursors)
8. [VLC](https://www.videolan.org/vlc/) (FOSS Media Player)
	1. or [MPV](https://mpv.io/) (FOSS mostly preferred by majority of people)
		1. [Modern UI for MPV](https://github.com/cyl0/MordenX)
	2. or [Rise Media Player](https://github.com/Rise-Software/Rise-Media-Player) (FOSS, Plays all kinds of media)
9. [Motrix](https://motrix.app/) (FOSS Download Manager)
10. [Notepad++](https://notepad-plus-plus.org/) (FOSS text editor with extra features and support)
11. Music Player of your choice 
	1. [Harmonoid](https://harmonoid.com/) (FOSS, YTM support, doesn't run on electron.js, runs on Flutter instead.)
	2. [Foobar2000](https://www.foobar2000.org/) (used among music enthusiast)
	3. [VOX Universal](https://vox.rocks/windows-music-player) (Great UI and has their cloud service to sync music across devices)
	4. [MusicBee](https://www.getmusicbee.com/) (supports plugins which expands the features)
	5. [Winamp](https://www.winamp.com/) (Known by many, and still use by many today)
	6. [Rise Media Player](https://github.com/Rise-Software/Rise-Media-Player) (FOSS, groove music but better and supports other media)
12. [Kdenlive](https://kdenlive.org/) (FOSS Video Editor)
13. [CompactGUI](https://github.com/IridiumIO/CompactGUI) (FOSS Compresses game files while still being playable)
14. [LenovoLegionToolKit](https://github.com/BartoszCichecki/LenovoLegionToolkit) FOSS alternative to Lenovo Vantage
15. [GOG Galaxy](https://www.gog.com/galaxy) All-in-One game launcher
	1. [Playnite](https://github.com/JosefNemec/Playnite) GOG Galaxy Alternative
		2. [Playnite Extensions](https://github.com/darklinkpower/PlayniteExtensionsCollection)
	3. [Lutris](https://lutris.net/)
16. [RTX Voice](https://www.nvidia.com/en-us/geforce/guides/nvidia-rtx-voice-setup-guide/) (AI noise suppression [Nvidia GPU only])