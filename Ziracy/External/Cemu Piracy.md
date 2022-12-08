    How to get games on Cemu
        Things you need
            For both methods
            If you want to do it legit
            If you just want to pirate the game
            Formats and Converters
            Abbreviations
        NUS Downloaders
            How To Use - USBHelper
                How to install on your WiiU
            How To Use - JNUSTool
                Notes
                Prerequisites
                Instructions
            How To Use - FunkiiU
        Other Tools
            CDecrypt2.0
            JWUDTool
                Prerequisites
                How to use

# How to get games on Cemu

Disclaimer. This is how to get games onto Cemu, NOT how to optimise games. Remember, Cemu is a WiiU Emulator so it is recommended to play ONLY WiiU games on it, not WiiU VC or Wii games. Please use the correct emulator for the system you want to play.

## Things you need

### For both methods

-   [Cemu](http://cemu.info)
-   [CemuHook](https://cemuhook.sshnuke.net/) (if it is available for the cemu version you are using)

### If you want to do it legit

-   A Homebrewed WiiU (follow the [WiiU.hacks.guide](http://wiiu.hacks.guide))
-   A homebrew to dump your Disc (or copy it from your WiiU - You will need to search for yourself to find a tutorial for this the [Cemu "Getting Started" guide is a place to start](https://wiki.cemu.info/wiki/Getting_Started))

### If you just want to pirate the game

-   A NUSDownloader - This is a piece of software that can download from the Nintendo Update Servers and _usually_ does most things for you

OR

-   A WUD/WUX/APP/RAW/Loadiine torrent (90% of the time, we don't recommend this)

### Formats and Converters

-   [CDecrypt2.0](https://cdn.discordapp.com/attachments/526469047890739220/539529151095373824/Cdecrypt_v2.0b.zip)
    
    -   Converts a WUP into RAW files
-   [JWUDTool](https://github.com/Maschell/JWUDTool/releases/latest) - Needs [Java](https://www.java.com/download/) installed to run
    
    -   Can convert
        -   WUD/WUX to WUP
        -   WUD/WUX to RAW (you will probably be using this method)
        -   WUD to/from WUX

### Abbreviations

-   WUD - WiiU Disc - a 1:1 copy of a Disc
-   WUX - A trimmed/"compressed" WUD
-   WUP - WiiU Package - An encrypted game in a WiiU installable format
-   RAW - Literally the Raw files of the game, otherwise known as "Unpacked", "Decrypted", "Loadiine" or "CCM" (Code, Content and Meta)
-   NUS - Nintendo Update Servers - Literally Nintendos Servers

## NUS Downloaders

The usual NUSDownloader we suggest for the newbies is [USBHelper + Launcher](). For the more terminal inclined (Or if you are using Linux/Mac), [Jnustool]() or [FunkiiU]() are better and simpler to setup than USBHelper + Launcher

### How To Use - USBHelper

1.  Download the following
    -   [USBHelper+Launcher Installer](https://github.com/FailedShack/USBHelperInstaller/releases/latest) (Download `USBHelperInstaller.exe`)
    -   If you are emulating on Cemu
        -   [Cemu](http://cemu.info/)
        -   [CemuHook](https://cemuhook.sshnuke.net/)
2.  Prepare your folders. You need the following folders on your largest drive as WiiU games can get up to and exceed 15GB each
    -   Work out where you want your WiiU games to be stored. Lets take `D:\WiiU Games` as an example
        -   In this folder you want 2 more folders. `Games` and `Updates and DLC`
    -   You also need a place where you want USBHelper to store its downloads. Lets use `D:\USBHelper Downloads` as an example.
        -   In this folder you want 2 more folders, `DL-Enc` and `DL-Dec`
    -   Lets also make a folder for Cemu `D:\Emulators\Cemu (version number)`
3.  Time to install USBHelper and get some frii gaems.
    1.  Run `USBHelperInstaller.exe` and install it to somewhere you have permissions to read and write from. The default path is ok for **most** users but lets install it to `D:\USBHelperLauncher`
    2.  Next your way through the menus and just use the default selection for the version of USBHelper it installs.
        -   **NOTE 1**: USBHelper and USBHelperLauncher are 2 different things. USBHelper is the main program where as USBHelperLauncher is a set of patches to make USBHelper run.
        -   **NOTE 2**: Your antivirus may detect it as a virus. This is a **FALSE POSITIVE** and USBHelper + Launcher is completely fine to install. If you want to be cautious and not install it, feel free to use an alternative downloader
    3.  On first run, USBHelper will ask a few things from you.
        -   A titlekey site... Just enter `titlekeys.ovh` into the box
        -   Where to save your files to... This is the `DL-Enc` folder you made (So `D:\USBHelper Downloads\DL-Enc` in this example)
        -   Your region... you first agree to the EULA then you select the region. Now, this is the region of games you are downloading, **not** the region of server it downloads from.
    4.  After you do all that, it will take a while to make a cache of things and download some inital files. THIS DOES TAKE A WHILE. Go play a game or something while you wait.
    5.  Hopefully after its done, you will see USBHelpers main screen. _IF_ it is in the wrong language you can right click its icon in your taskbar (near your clock) and select your language from there.
    6.  Before you start adding games you your queue, we need to set up your "Extraction Folder". Click on the "Set extraction directory" button at the bottom of the window and select your `DL-Dec` folder (So `D:\USBHelper Downloads\DL-Dec` in this example)
    7.  Now you can add games to your queue. To do this, right click a game and "Add to download queue" (If there is DLC and/or Updates, it will ask you about these as well)
    8.  Hit the "Download" button to start the queue and now you just need to wait. If you have any issues, Feel free to join the [CemuP Discord](https://discord.gg/Tw65yaE) and ask in the appropriate channel.
        -   Something you can do while you wait is to quickly set up Cemu following BSoD Gamings optimisation guide
        -   also set up your "Game Path" in Cemu to your `Games` Folder
    9.  WAIT... just WAIT .... Tick tock goes the clock... BING, a notification that the downloads have finished
        -   WiiU Users can stop here and head down to "[How to install on your WiiU](https://www.reddit.com/r/CemuPiracy/wiki/tutorial/#wiki_how_to_install_on_your_wiiu)"
    10.  Right click on the game and "Unpack (Loadiine)" and wait for it to finish what it needs to do
    11.  You will then find in your `DL-Dec` folder some more folders. You will find a folder for a game, one for the DLC (if it has DLC) and another for the update (if it has an update)
    12.  This is where most users mess up and skip this step. You want to **MOVE** (so cut and paste) the update and the DLC into your `Updates and DLC` Folder and then **MOVE** the game folder into your `Games` folder.
    13.  In Cemu, go `File > Install Update or DLC` and select the `Game/meta/meta.xml` file of the update and DLC (so for Mario Kart 8 for example will be something like `D:\WiiU Games\Updates and DLC\Mario Kart 8 [DLC]\meta\meta.xml`)
        -   You can delete that folder **AFTER** you install it to save on some space if you wish
    14.  You can now play your game from the Cemu games list

#### How to install on your WiiU

1.  Put your appropriately set up and sized SD card in your PC (so your CFW and WupInstaller)
2.  Right click the game in USBHelper and "Copy to SD"
3.  Put SD card in WiiU
4.  Load up CFW
5.  Load up WupInstaller
6.  Install game
7.  ????
8.  Profit

### How To Use - JNUSTool

#### Notes

JNUSTool does not make fake (unsigned) tickets, so it is useless for WiiU Users, Use USBHelper or FunkiiU

#### Prerequisites

-   Java
-   [Jnustool](https://github.com/Maschell/JNUSTool/releases/latest) (Get the zip)
-   _Some_ command line knowledge (so Command Prompt, Powershell, Terminal, etc)
-   [The list of Title IDs and Keys](http://vault.titlekeys.ovh/listing/)
-   The **WiiU common key**, Do a google search for this, it starts with `D7`

#### Instructions

1.  Extract the zip to a folder on your largest drive, Lets make that `D:/JNUSTool` for this example
2.  Now you should have `JNUSTool.jar` (or something similar) and a `config` file.
3.  Open that `config` file in Notepad or some other text editor. Change the line that says `[commonkey]` into the WiiU Common Key (without any spaces). Save and exit.
4.  Open the "Title ID and Key list" and search for the game you want.
5.  Open the command prompt (if you aren't already in it) and you can run the following to get the raw files for Cemu `java -jar Jnustool.jar titleID titleKey -file /.*`
6.  When it finishes, run it a few more times as JNUSTool only checks files that already exist, not after it finished downloading.

### How To Use - FunkiiU

**Irastris** from the [Discord](https://discord.gg/Tw65yaE) did a great writeup on FunkiiU, Have a read of it [here](https://gist.github.com/Irastris/31766414a981a056d49c1242a019829a)

## Other Tools

### CDecrypt2.0

Currently in constuction

### JWUDTool

#### Prerequisites

-   Java
-   [JWUDTool](https://github.com/Maschell/JWUDTool/releases/latest)
-   A Game WUD/WUX with a `*.key` file
-   _Some_ command line knowledge (so Command Prompt, Powershell, Terminal, etc)
-   The **WiiU common key**, Do a google search for this, it starts with `D7`

#### How to use

1.  Make a copy of the `.key` file and call it `game.key`
2.  Open your command prompt or terminal and work out if you want it for Cemu or a WiiU

You will need the following commands

-   WiiU - `java -jar JWUDTool.jar -in filename.wud (or wux) -commonkey WiiU_Commonkey -out "wup" -extract all`
-   Cemu - `java -jar JWUDTool.jar -in filename.wud (or wux) -commonkey WiiU_Commonkey -out "raw" -decryptFile /.*`