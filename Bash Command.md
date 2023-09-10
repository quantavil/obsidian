## File rename

This Bash command renames files from `.ext1` to `.ext2` with sequential numbering in the filename.

```bash
count=1

for file in *.ext1; do
    mv "$file" "Filename-${count}.ext2"
    ((count++))
done
```


## Batch File Renamer Script

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