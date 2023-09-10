## File Extension Rename

This Bash command renames files from `.ext1` to `.ext2` with sequential numbering in the filename.

```bash
count=1

for file in *.ext1; do
    mv "$file" "Filename-${count}.ext2"
    ((count++))
done
```


## Batch Script to Remove Specific Strings from File Names

Description: This Windows batch script is designed to rename files in a specified directory by removing specific search strings from their filenames.

```bash
@echo on
setlocal enabledelayedexpansion

set "searchStrings=@ImTgLoki @TgLokii"

rem Loop through all files in the current directory
for %%F in (*) do (
    set "filename=%%~nF%%~xF"
    
    rem Initialize the new filename with the original filename
    set "newFilename=!filename!"
    
    rem Loop through each search string and remove it from the new filename
    for %%S in (%searchStrings%) do (
        set "newFilename=!newFilename:%%S=!"
    )
    
    rem Check if the filename has changed
    if not "!filename!"=="!newFilename!" (
        rem Rename the file
        ren "%%F" "!newFilename!"
        echo Renamed "%%F" to "!newFilename!"
    )
)

endlocal

```

**Code Explanation (Bullet Points):**

1. `@echo on`: This command turns on command echoing, which displays the executed commands in the console as they are run. This can be helpful for debugging.

2. `setlocal enabledelayedexpansion`: This command enables delayed variable expansion, allowing us to manipulate variables within loops.

3. `set "searchStrings=@ImTgLoki @TgLokii"`: Set the `searchStrings` variable to a space-separated list of strings that you want to remove from file names.

4. The script uses a `for` loop to iterate through all files in the current directory (`*`):

    - `set "filename=%%~nF%%~xF"`: Extract the filename with its extension from the current file being processed and store it in the `filename` variable.

    - `set "newFilename=!filename!"`: Initialize the `newFilename` variable with the original filename.

    - Another `for` loop is nested inside the outer loop to iterate through each search string in the `searchStrings` list:

        - `set "newFilename=!newFilename:%%S=!"`: This line removes the current search string (`%%S`) from the `newFilename`. The `!newFilename:%%S=!` syntax is used to perform a string replacement, effectively removing any occurrence of the search string.

    - `if not "!filename!"=="!newFilename!"`: This conditional statement checks if the filename has changed after the removal of the specified strings.

        - `ren "%%F" "!newFilename!"`: If the filename has changed, it renames the file with the updated `newFilename`.

        - `echo Renamed "%%F" to "!newFilename!"`: It also echoes a message to the console to indicate the renaming action.

5. `endlocal`: This command ends the local scope and releases the environment changes made within the script.

In summary, this batch script iterates through files in the current directory, removes specified strings from their names, and renames them with the updated names if changes are detected. It provides feedback by echoing the renaming actions to the console for each file.
## Batch Script to Remove Trailing Whitespaces from File Names

```bash
@echo off
setlocal enabledelayedexpansion

rem Set the directory path where you want to remove trailing whitespaces
set "directory=C:\Path\To\Your\Directory"

rem Iterate over files in the directory
for %%F in ("%directory%\*") do (
    set "filename=%%~nF"
    
    rem Remove trailing whitespaces from the filename
    for /l %%a in (1,1,31) do if "!filename:~-1!"==" " set "filename=!filename:~0,-1!"

    rem Rename the file with the updated filename
    ren "%%F" "!filename!%%~xF"
)

endlocal

```

**Title:** Batch Script to Remove Trailing Whitespaces from File Names

**Description:** This batch script is designed to remove trailing whitespaces from the names of files within a specified directory. It uses a for loop structure to iterate through each file in the directory and performs the necessary renaming to eliminate any trailing spaces.

**Code Explanation (Bullet Points):**

1. `@echo off`: This command turns off command echoing, which prevents the commands themselves from being displayed in the console as they are executed.
    
2. `setlocal enabledelayedexpansion`: This command enables delayed variable expansion, allowing us to manipulate variables within loops.
    
3. `set "directory=C:\Path\To\Your\Directory"`: Set the `directory` variable to the path of the directory where you want to remove trailing whitespaces. Replace `C:\Path\To\Your\Directory` with your actual directory path.
    
4. `for %%F in ("%directory%\*") do`: This loop iterates through all files (`%%F`) in the specified directory.
    
5. `set "filename=%%~nF"`: Extract the filename without the extension from the current file being processed and store it in the `filename` variable.
    
6. The following code block is a nested loop that removes trailing whitespaces from the `filename`:
    
    - `for /l %%a in (1,1,31) do`: This loop runs 31 times (adjustable if needed).
        
    - `if "!filename:~-1!"==" "`: It checks if the last character of the `filename` is a whitespace.
        
    - `set "filename=!filename:~0,-1!"`: If the last character is a whitespace, it removes it from the `filename` by extracting all characters except the last one.
        
7. `ren "%%F" "!filename!%%~xF"`: After removing trailing whitespaces from the `filename`, this command renames the current file by combining the updated `filename` with its original file extension (`%%~xF`).
    
8. `endlocal`: This command ends the local scope and releases the environment changes made within the script.
    

In summary, this batch script processes files in a specified directory, removes trailing whitespaces from their names, and renames them with the cleaned filenames while preserving their original extensions.