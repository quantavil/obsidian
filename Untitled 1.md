### File and directory commands

1. **pwd** The pwd(Present Working Directory) command is used to print the name of the present/current working directory starting from the root.
   ```bash
   $ pwd
   /home/sj/Desktop/Linux
   ```

2. **ls**: The `ls` command is used to list files or directories. It also accepts some flags or options that changes how files or directories are listed in your terminal.

    ```bash
     Syntax:
     ls [flags] [directory]

     Example:
     $ ls
     bin dev lib libx32 mnt  

     //Listing files & directories with time in a rever order
     $ ls -ltr
     drwxr-xr-x 2 sj sj 4096 May 14  2020 Videos
     drwxr-xr-x 2 sj sj 4096 May 14  2020 Templates
     drwxr-xr-x 2 sj sj 4096 May 14  2020 Public

     //Home directory
     $ ls ~
     Desktop    Downloads  Pictures  Sudheer    test   test.txt
     Documents  Music      Public    Templates  test1  Videos
    ```

    Below are the list of possible options for `ls` command,

    ```cmd
    -a Show all (including hidden)
    -R To list subdirectories and their files recursively
    -r Reverse order
    -t Sort by last modified
    -S Sort by file size
    -l Long listing format
    -1 One file per line
    -m Comma-­sep­arated output
    -Q Quoted output
    -i To list directory contents along with inode number
    ```

3. **mkdir** The mkdir(make directory) command allows users to create directories or folders.

   ```bash
   $ mkdir ubuntu
   $ ls
   ubuntu
   ```

   The option '-p' is used to create multiple directories or parent directories at once.

   ```bash
   $ mkdir -p dir1/dir2/dir3
   $ cd dir1/dir2/dir3
   ~/Desktop/Linux/dir1/dir2/dir3$
   ```

4. **rmdir**: The rmdir(remove directories) is used to remove _empty_ directories. Can be used to delete multiple empty directories as well. Safer to use compared to `rm -r FolderName`. This command can also be forced to delete non-empty directories.

   1. Remove empty directory:

   ```bash
   rmdir FolderName
   ```

   2. Remove multiple directories:

   ```bash
   rmdir FolderName1 FolderName2 FolderName3
   ```

   3. Remove non-empty directories:

   ```bash
   rmdir FolderName1 --ignore-fail-on-non-empty
   ```

   4. Remove entire directory tree. This command is similar to `rmdir a/b/c a/b a`:

   ```bash
   rmdir -p a/b/c
   ```

5. **rm**: The rm(remove) command is used to remove objects such as files, directories, symbolic links etc from the file system.
   1. Remove file: The rm command is used to remove or delete a file
   ```bash
   rm file_name
   ```
   2. Remove file forcefully: The rm command with -f option is used for removal of file without prompting for confirmation.
   ```bash
   rm -f filename
   ```
   3. Remove directory: The rm command with -r option is used to remove the directory and its contents recursively.
   ```bash
   rm -r myDir
   ```
   4. Remove directory forcefully: The rm command with -rf option is used to forcefully remove directory recursively.
   ```bash
   rm -rf myDir
   ```
6. **touch**: The touch command is is used to create, change and modify timestamps of a file without any content.

```bash
touch foo.txt          # Create file or update existing files modified timestamp
touch foo.txt bar.txt  # Create multiple files
touch {foo,bar}.txt    # Create multiple files
touch test{1..3}       # Create test1, test2 and test3 files
touch test{a..c}       # Create testa, testb and testc files

mktemp                 # Create a temporary file
```


**7. Cat**
   1. **Create a file:** Used to create a file with specific name, content and press exit using `CTRL + D`
       ```bash
       cat > file_name1.txt
       Hello, How are you?
       ```
   2. **View file contents:** You can view contents of a single or more files by mentioning the filenames.

       ```bash
       cat file_name1 file_name2
       ```
   3. **More & Less options:** If a file having a large number of content that won’t fit in the output terminal then `more` & `less` options can be used to indiate additional content.

       ```bash
       cat file_name1.txt | more
       cat file_name1.txt | less
       ```

## Text Processing

### Grep

The grep (**g**lobal **r**egular **e**xpression **p**rint) enables searching through text in a file or a standard output. The basic syntax is:

```
grep <search string> <filename>
```

**Options Description**
**-c** : This prints only a count of the lines that match a pattern
**-h :** Display the matched lines, but do not display the filenames.
**-i :** Ignores, case for matching
**-l :** Displays list of a filenames only.
**-n :** Display the matched lines and their line numbers.
**-v :** This prints out all the lines that do not matches the pattern
**-e exp :** Specifies expression with this option. Can use multiple times.
**-f file :** Takes patterns from file, one per line.
**-E :** Treats pattern as an extended regular expression (ERE)
**-w :** Match whole word
**-o :** Print only the matched parts of a matching line,
 with each such part on a separate output line.

**-A n** **:** Prints searched line and nlines after the result.
**-B n :** Prints searched line and n line before the result.
**-C n :** Prints searched line and n lines after before the result.




















```
$ cat orange | tr -d "," | tr -s ";" ";" | sort -t ";" -nk2 | cut -d ";" -f1,3 | tail -2
```

```
$ cat orange | tr -d "," | tr -s ";" ";" | sort -t ";" -k4 | grep -c "Grocery"
2
```


```
$ cat orange | tr -d "," | tr -s ";" ";" | sort -t ";" -k4 | cut -d ";" -f4 | uniq -c | tail -2 | head -1
      2 Grocery

```

```
$ cat orange | tr -d "," | tr -s ";" ";" | sort -t ";" -k4 | cut -d ";" -f4 | uniq -d | wc -l
3

```