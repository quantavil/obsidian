
->This guide is intended to explain how to download and use Fabric/Forge mods on Minecraft.<-
->Curated by Big Iron#4218<-
***
[TOC2]
***

##Before you start
###📌Prerequisites
If you want to play a specific version of Minecraft, you'll need to have the compatible version of the JRE (Java Runtime Environment).
For this guide, we'll be using the ones provided by [Adoptium](https://adoptium.net/temurin/releases), which are based upon OpenJDK. 
Minecraft Version | JRE Version
------ | ------
1.16.5 and older | Java 8
1.17.X | Java 16
1.18 and newer | Java 17

###🧰Tools
Here is a list of the tools we are going to use during this guide. All of them are open-source and free to use.
Tool | Description
------ | ------
[MultiMC](https://multimc.org/)   | An alternative to the official Minecraft launcher, made to easily manage and mod various instances.
[PolyMC](https://polymc.org/) | A fork of MultiMC, with enhanced features, like an inbuilt mod downloader.
[UltimMC](https://github.com/UltimMC/Launcher) | A fork of MultiMC, made for `cracked` players who don't own a legit copy of Minecraft.
[Fabric Loader](https://fabricmc.net/) | The modloader used for `Fabric` mods.
[Forge Loader](https://files.minecraftforge.net/net/minecraftforge/forge/) | The  modloader used for `Forge` mods.

!!!warning Unsafe cracked launchers
	Avoid using closed source third-party launchers (`TLauncher` is a common example).
	Since nobody can look at the code, the developers could insert malicious code, that could potentilally harm your devices.
	I suggest using `UltimMC`, as stated above.

###🌐Websites
These are the webisites we are going to use to download mods.
Website | Sescription
------ | ------
[Modrinth](https://modrinth.com/mods) | The newest website for Minecraft mods. It has filters to help you find what you want easily.
[Curseforge](https://www.curseforge.com/minecraft/mc-mods) | The old website for Minecrft mods. The UI is less intuitive, and the filters are barely usable.

!!!info
	Since the release of Fabric, Modrinth has become the best platform for mods, and many of those hosted on Curseforge have migrated to it.
	That's why I suggest you use this newer and better source for all your modding needs.
***

##Installation Walkthrough
###☕Installing the JRE
So, you know what version of Minecraft you want to play on. Then, be ready to download the compatible JRE:
1. Go to the [Adoptium](https://adoptium.net/temurin/releases) website;
2. Select your OS under `Operating System`;
3. Select `JRE` under `Package Type`;
4. Select the version you need under `Version`;
5. Download the version compatible with your `Architecture`.
!!!note Installer vs Archive
	There isn't much of a difference, other than that the installer is going to try and download the JRE to the default folder for Java.
	If you want to install the JRE to another folder, using the archive version is suggested (Open archives using a compatible tool, like [7zip](https://www.7-zip.org/download.html)).
###📦Installing Minecraft
####💵Legit
If you own a legit copy of Minecraft, you'll want to install [PolyMC](https://polymc.org/download/) .
Choose the version compatible with your OS, extract the archive and start the executable.
1. Choose your language (not all translations are 100% complete);
2. Choose your default Java version (this one will be used for all your instances, but you can specify other versions when making an instance);
3. Set the Minimum/Maximum memory allocation to a multiple of 512 (RAM deticated to Minecraft, do not dedicate more than half of your RAM);
4. Once  you are on the main menu, click the `Profiles` button on the top right corner and select `Manage Accounts`;
5. Select `Add Microsoft` and follow the on-screen instructions to add your MC account.

You have now completed the setup of PolyMC. Now, we'll see how to add a playable instance.
1. To create a Minecraft instance, click on the `Add Instance` button on the top left corner;
2. On the left bar, select the type of instance you want;
3. On the bottom, select the version and the modloader, then click `OK` to create it;
4. Double click on the instance to run it and play.

!!!Info Starting the game in fullscreen
	To start any instance in fullscreen, click the `Settings` button, then go to `Minecraft` and enable the `Start Minecraft maximized` option.

####🏴‍☠️Cracked
If you don't own a legit copy of Minecraft, you'll want to install [UltimMC](https://nightly.link/UltimMC/Launcher/workflows/main/main).
Almost all the steps are like the ones for the legit version, except:
* When adding an account, put your username in the `Email` section and a random password;
* Before creating an instance, click the `Settings` button, then go to `Java` and insert `-Dauthlibinjector.noShowServerName` into `JVM arguments`.
***

##Modding Walkthrough
!!!info
	If you are using PolyMC, you can click the `Download mods` button inside of an instance's menu to open the in-built mod downloader.
###📜Fabric
Add Fabric Loader to a new instance:
1. Right click on a Vanilla (mod-less) instance, click `Edit Instance`;
2. Select the `Version` tab, then click `Install Fabric` on the right side;
3. Choose the newest version of the Fabric Loader, compatible with the instance version.

To download mods to a Fabric instance:
1. Go on [Modrinth](https://modrinth.com/mods);
2. Search for a mod (you can use filters to refine your search);
3. Download the mod (usually a `.jar` file, do not try and extract it);
4. Copy and paste it inside the `mods` folder of the Fabric instance.

###🔨Forge
Add Forge Loader to a new instance:
1. Right click on a Vanilla (mod-less) instance, click `Edit Instance`;
2. Select the `Version` tab, then click `Install Forge` on the right side;
3. Choose the newest version of the Forge Loader, compatible with the instance version.

To download mods to a Forge instance:
1. Go on [Modrinth](https://modrinth.com/mods);
2. Search for a mod (you can use filters to refine your search);
3. Download the mod (usually a `.jar` file, do not try and extract it);
4. Copy and paste it inside the `mods` folder of the Forge instance.

###🗃️Modpacks
To download any type of modpack (Fabric/Forge):
1. Create a new instance;
2. When choosing the type, select `Curseforge`;
3. Use the search bar to find your modpack;
4. Choose the version of the modpack in the bottom right;
5. Click `OK` and wait for the mods to be automatically downloaded

You have now downloaded a modpack. Double click on the instance to ply it.
!!!note Slow game start
	When playing with many mods, the game might take longer to load, and suffer performance drops.
	Is that's the case, I suggest you increase the dedictaed RAM, but never allocate more than half of your device's available RAM.
***