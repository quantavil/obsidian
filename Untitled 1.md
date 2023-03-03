## File permissions

Since Linux is a multi-user operating system, it is necessary to provide security to prevent people from accessing each other’s confidential files. So Linux divides authorization into 2 levels,

1.  **Ownership:** Each file or directory has assigned with 3 types of owners i. **User:** Owner of the file who created it. ii. **Group:** Group of users with the same access permissions to the file or directory. iii. **Other:** Applies to all other users on the system
    
2.  **Permissions:** Each file or directory has following permissions for the above 3 types of owners.
    
    i. **Read:** Give you the authority to open and read a file and lists its content for a directory.
    
    ii. **Write:** Give you the authority to modify the contents of a file and add, remove and rename files stored in the directory.
    
    iii. **Execute:** Give you the authority to run the program in Unix/Linux.
    
    The permissions are indicated with below characters,
    
    ```
      r = read permission
    
      w = write permission
    
      x = execute permission
    
      \- = no permission
    ```
    
    The above authorization levels represented in a diagram
[![](https://github.com/sudheerj/Linux-cheat-sheet/raw/master/images/permissions.png)](https://github.com/sudheerj/Linux-cheat-sheet/blob/master/images/permissions.png)

There is a need to restrict own file/directory access to others.

**Change access:** The `chmod` command is used to change the access mode of a file. This command is used to set permissions (read, write, execute) on a file/directory for the owner, group and the others group.

```batchfile
chmod [reference][operator][mode] file...

Example
chmod ugo-rwx test.txt
```

There are 2 ways to use this command,

1.  **Absolute mode:** The file permissions will be represented in a three-digit octal number.
    
    The possible permissions types represented in a number format as below.

| Permission Type | Number | Symbol |
| --- | --- | --- |
| No Permission | 0 | \--- |
| Execute | 1 | \--x |
| Write | 2 | \-w- |
| Execute + Write | 3 | \-wx |
| Read | 4 | r-- |
| Read + Execute | 5 | r-x |
| Read + Write | 6 | rw- |
| Read + Write + Execute | 7 | rwx |

Let's update the permissions in absolute mode with an example as below,

```batchfile
 chmode 764 test.txt
```

2.  **Symbolic mode:** In the symbolic mode, you can modify permissions of a specific owner unlike absolute mode.
    
    The owners are represented as below,
    
| Owner | Description |
| --- | --- |
| u | user/owner |
| g | group |
| o | other |
| a | all |

and the list of mathematical symbols to modify the file permissions as follows,

| Operator | Description |
| --- | --- |
| + | Adds permission |
| \- | Removes the permission |
| \= | Assign the permission |
    

**Changing Ownership and Group:** It is possible to change the the ownership and group of a file/directory using `chown` command.

```batchfile
chown user filename
chown user:group filename

Example:
chown John test.txt
chown John:Admin test.txt
```

**Change group-owner only:** Sometimes you may need to change group owner only. In this case, chgrp command need to be used

```batchfile
chgrp group_name filename

Example:
sudo chgrp Administrator test.txt
```
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

### rm

The rm(remove) command is used to remove objects such as files, directories, symbolic links etc from the file system.

```bash
# To remove all files and subdirs in <dir>:
rm -rf <dir>

# To ignore non-existent files:
rm -f <dir>

# To remove a file with this inode:
find /tmp/ -inum 6666 -exec rm -i '{}' \;

 tldr:rm 
# rm
# Remove files or directories.
# See also: `rmdir`.
# More information: <https://www.gnu.org/software/coreutils/rm>.

# Remove specific files:
rm path/to/file1 path/to/file2 ...

# Remove specific files ignoring nonexistent ones:
rm -f path/to/file1 path/to/file2 ...

# Remove specific files [i]nteractively prompting before each removal:
rm -i path/to/file1 path/to/file2 ...

# Remove specific files printing info about each removal:
rm -v path/to/file1 path/to/file2 ...

# Remove specific files and directories [r]ecursively:
rm -r path/to/file_or_directory1 path/to/file_or_directory2 ...
```

### touch

The touch command is is used to create, change and modify timestamps of a file without any content.

```bash
touch foo.txt          # Create file or update existing files modified timestamp
touch foo.txt bar.txt  # Create multiple files
touch {foo,bar}.txt    # Create multiple files
touch test{1..3}       # Create test1, test2 and test3 files
touch test{a..c}       # Create testa, testb and testc files

mktemp                 # Create a temporary file
```


### Cat

```bash
# To display the contents of a file:
cat file

# To display multiple file
cat file1 file2

# display content of all txt file 
cat *.txt

# To display file contents with line numbers
cat -n file

# To display file contents with line numbers (blank lines excluded)
cat -b file

# Supress repeated empty lines
cat -s file

# Append to already existing file
cat >> file

# Write to the file
cat > file

# Print the contents of a file to the standard output:
cat path/to/file

# Concatenate several files into an output file:
cat path/to/file1 path/to/file2 ... > path/to/output_file

# Append several files to an output file:
cat path/to/file1 path/to/file2 ... >> path/to/output_file

# display content in reverse order
tac file

# display large content 
cat file_name1.txt | more
cat file_name1.txt | less
```


## Text Processing

### Head 
Use the **`head`** command to truncate long outputs. The command can truncate files, for example:

```bash
head <filename>

head -n 5 bar.txt  # Prints the first ‘num’ lines
head -c 5 bar.txt    #  Prints the first ‘num’ bytes , Newline count as a single character
```

### Tail
The Linux tail command does the opposite of **`head`**. Use the command to show the last ten lines of a file:

```bash
tail <filename>
tail -n 5 bar.txt  # Prints the last ‘num’ lines
tail -c 5 bar.txt    #  Prints the last ‘num’ bytes , Newline count as a single character
```


### Diff

Display the differences between two files, or each corresponding file in two directories.  Each set of differences is called a "diff" or "patch".

```bash
diff file1 file2

diff -c file1 file2         # To view differences in context mode
diff -u file1 file2         #  To view differences in unified mode
diff -i file1 file2 # To make this command _case in-sensitive_

# To view the differences between two files:
diff -u file-1 file-2

# To view the differences between two directories:
diff -ur dir-1 dir-2

# To ignore whitespace:
diff -ub file-1 file-2

# To ignore blank lines:
diff -uB file-1 file-2

# To ignore the differences between uppercase and lowercase:
diff -ui file-1 file-2

# To report whether the files differ:
diff -q file-1 file-2

# To report whether the files are identical:
diff -s file-1 file-2
```

**Example :**

```bash
$ ls
a.txt  b.txt

$ cat a.txt
Gujarat
Uttar Pradesh
Kolkata
Bihar
Jammu and Kashmir

$ cat b.txt
Tamil Nadu
Gujarat
Andhra Pradesh
Bihar
Uttar pradesh
```

```bash
$ diff a.txt b.txt
0a1        # 0a1 means after lines 0 you have to add Tamil Nadu  to file 'a' to match the file 'b' line 1.
> Tamil Nadu
2,3c3      # from line 2 to 3 in file 'a' changes needed to match line 3 in file 'b'
< Uttar Pradesh # remove from file 'a'
< Kolkata       # remove from file 'a'
---
> Andhra Pradesh      # add to file 'a'
5c5
< Jammu and Kashmir    # remove from file 'a'
---
> Uttar pradesh      # add to file 'a'

```

```bash
$ diff -c a.txt b.txt
*** a.txt       Fri Mar  3 11:50:53 2023
--- b.txt       Fri Mar  3 11:45:22 2023
***************
*** 1,5 ****
  Gujarat
! Uttar Pradesh
! Kolkata
  Bihar
! Jammu and Kashmir
--- 1,5 ----
+ Tamil Nadu
  Gujarat
! Andhra Pradesh
  Bihar
! Uttar pradesh

```

```bash
$ diff -u a.txt b.txt
--- a.txt       2023-03-03 11:50:53.986117400 +0530
+++ b.txt       2023-03-03 11:45:22.256579800 +0530
@@ -1,5 +1,5 @@
+Tamil Nadu
 Gujarat
-Uttar Pradesh
-Kolkata
+Andhra Pradesh
 Bihar
-Jammu and Kashmir
+Uttar pradesh

```

### Comm

Compare two sorted files line by line. Output the lines that are common, plus the lines that are unique.

```bash
# Produce three tab-separated columns: lines only in first file, lines only in second file and common lines:

comm file1 file2 

# Produce two tab-separated columns , where column 1 is supressed
comm -l1 file1 file2

# Print only lines common to both files, reading one file from `stdin`:
cat file1 | comm -12 - file2

# Print lines only found in second file, when the files aren't sorted:
comm -13 <(sort file1) <(sort file2)
```

Options for comm command:

1. -1 :suppress first column(lines unique to first file).
2. -2 :suppress second column(lines unique to second file).
3. -3 :suppress third column(lines common to both files).

**Example :**

```bash
// displaying contents of file1 //
$cat file1.txt
Apaar 
Ayush Rajput
Deepak
Hemant

// displaying contents of file2 //
$cat file2.txt
Apaar
Hemant
Lucky
Pranjal Thakral
```

```bash
$ comm file1 file2
        Apaar
Apaar
Ayush Rajput
Deepak
                Hemant
        Lucky
        Pranjal Thakral
```

```bash
$ cat file1 | comm -12 - file2
Hemant
```


### Cut

The **`cut`** command is a command-line utility that allows you to cut out sections of a specified file or piped data and print the result to standard output.
| Option | Description |
| --- | --- |
| **`-f (--fields=LIST)`** | Select using a specified field, a field set, or a field range. |
| **`-b (--bytes=LIST)`** | Select using a specified byte, a byte set, or a byte range. |
| **`-c (--characters=LIST)`** | Select using a specified character, a character set, or a character range. |
| **`-d (--delimiter)`** | Used to specify a delimiter to use instead of the default TAB delimiter. |

```bash
# Print a range of each line with a specific delimiter:
command | cut -d "," -f 1,2

# Command prints field from first to fourth of each line from the file.
cut -d " " -f 1-4 foo.txt

# Print a range of each line of the specific file:
cut -c 1 foo.txt

```

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

```bash
grep 'foo' bar.txt                         # Search for 'foo' in file 'bar.txt'
grep 'foo' bar -r|--recursive              # Search for 'foo' in directory 'bar'
grep 'foo' bar -R|--dereference-recursive  # Search for 'foo' in directory 'bar' and follow symbolic links
grep 'foo' bar -l|--files-with-matches     # Show only files that match
grep 'foo' bar -L|--files-without-match    # Show only files that don't match
grep 'Foo' bar -i|--ignore-case            # Case insensitive search
grep 'foo' bar -x|--line-regexp            # Match the entire line
grep 'foo' bar -v|--invert-match           # Show only lines that don't match
grep 'foo' bar -c|--count                  # Count the number lines that match
grep 'foo' bar -n|--line-number            # Add line numbers
grep 'foo' bar --colour                    # Add colour to output


grep "^unix" geekfile.txt             # match the lines which start with the given string or pattern.
```

```bash
# finding file whose 3rd character is 'e'
 ls -1 | grep -E '^..[e].*' 
```




















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