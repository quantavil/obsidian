## Autorun script at startup

Method 1:

-   Open startup folder: open `Run` window by `Win+R` and then write `shell:startup` and enter.
-   It'll open explorer at something like this path: `C:\Users\{username}\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup`
-   Copy a script (`.ahk`) -> go to that `Startup` folder -> right-click and select `Paste shortcut`.

OR

Method 2:

-   Put [`script_autorun_startup.vbs`](https://github.com/GorvGoyl/Autohotkey-Scripts-Windows/blob/master/script_autorun_startup.vbs) at startup folder. Make sure to put the correct path of your ahk scripts in that file first.

### [](https://gourav.io/blog/autohotkey-scripts-windows#ahk-communities-to-get-help)

### AHK communities to get help

-   [https://www.reddit.com/r/AutoHotkey/](https://www.reddit.com/r/AutoHotkey/)
-   [https://www.autohotkey.com/boards/](https://www.autohotkey.com/boards/)

## Look up selected text

script: [look_up.ahk](https://github.com/GorvGoyl/Autohotkey-Scripts-Windows/blob/master/look_up.ahk)

use `alt+g` to open selected text in the browser and do a google search or visit the site (if it's url). It's one of the most frequent scripts I use on a regular basis. Especially to quickly google some error from the terminal when programming. Works everywhere.

**Assign a different shortcut:**

To assign a different shortcut, replace `!g` (here `!` means `Alt` so `!g` = `Alt+G`) in the script with your desired [key combo](https://www.autohotkey.com/docs/Hotkeys.htm#Symbols) and run again. All running scripts can be found in the Windows tray menu.

To use a different browser instead of Microsoft Edge, Add its path instead of `C:\\Program Files (x86)\\Microsoft\\Edge\\Application\\msedge.exe` in the script.

