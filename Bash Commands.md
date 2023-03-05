- [[#File permissions|File permissions]]
- [[#File and directory commands|File and directory commands]]
	- [[#File and directory commands#pwd & cd|pwd & cd]]
	- [[#File and directory commands#ls|ls]]
	- [[#File and directory commands#cp & mv|cp & mv]]
	- [[#File and directory commands#mkdir|mkdir]]
	- [[#File and directory commands#rmdir|rmdir]]
	- [[#File and directory commands#rm|rm]]
	- [[#File and directory commands#touch|touch]]
	- [[#File and directory commands#echo|echo]]
		- [[#echo#printf|printf]]
	- [[#File and directory commands#Cat|Cat]]
	- [[#File and directory commands#Head  & tail|Head  & tail]]
	- [[#File and directory commands#Diff|Diff]]
	- [[#File and directory commands#Comm|Comm]]
- [[#Text Processing|Text Processing]]
	- [[#Text Processing#Cut|Cut]]
	- [[#Text Processing#Grep|Grep]]
	- [[#Text Processing#sed|sed]]
	- [[#Text Processing#tr|tr]]
	- [[#Text Processing#sort|sort]]
	- [[#Text Processing#uniq|uniq]]
	- [[#Text Processing#wc|wc]]


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

## File and directory commands

### pwd & cd

**pwd**
```bash
$ pwd
# Print name of current/working directory.
```

**cd**

```bash
# Go to the given directory:
cd path/to/directory

# Go to home directory of current user:
cd

# Go up to the parent of the current directory:
cd ..

# Go to the previously chosen directory:
cd -

```

### ls
The `ls` command is used to list files or directories. It also accepts some flags or options that changes how files or directories are listed in your terminal.

```bash
# To display everything in <dir>, excluding hidden files:
ls <dir>

# To display everything in <dir>, including hidden files:
ls -a <dir>

# To display files, sorted by size:
ls -S <dir>

# To display directories only:
ls -d */ <dir>

# To display directories only, include hidden:
ls -d .*/ */ <dir>

# To display all files sorted by changed date, most recent first:
ls -ltc 

# Long format list of all files, sorted by modification date (oldest first):
ls -ltr

# To display files sorted by create time:
ls -lt

# To display files in a single column:
ls -1

# To show all the subtree files (Recursive Mode):
ls -R

# List files one per line:
ls -1

# List all files, including hidden files:
ls -a

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

```bash
# list all files contains 3 chars.
ls ???
# list all files contains two chars and first character should be x.
ls x?
# To display list of files having atleast 3 chars.
ls ???*
# list of all files where filename starts with f or y or c.
ls [fyc]*
# list of all files where filename not starts with f or y or c.
ls [!fyc]*
# list of all files name starts with lower case alphabates.
ls [a-z]* /  ls [[:lower:]]*
# list of all files name starts with Upper case alphabates.
ls [A-Z]* /  ls [[:upper:]]*
# list of all the filename starts with digits.
ls [0-9]* /  ls [[:digit:]]*
# list of all file starts with special symbols.
ls [![:alnum:]]*

----------------------------------------------------------------
? - single character
* -zero or more occurence (Multiple character)
.(dot) represents 1 or more characters.
\| indicates 'or'.
clear - to clear screen.
[a-z]* - search for all the range of values
ls [f]*
ls [0-9][a-z]*
[!a-z]* - other than alphabet

```


### cp & mv

cp- copy content from one file to another.
mv- move file from one to destination * data overwrite 

```bash
# Copy the file file1.txt to file2.txt in the current directory
cp file1.txt file2.txt

# Copy the directory dir1 and all its contents to dir2 in the current directory
cp -R dir1 dir2

# Move the file file1.txt to the directory dir1 in the current directory
mv file1.txt dir1/

# Rename the file file1.txt to file2.txt in the current directory
mv file1.txt file2.txt

cp file1 file2 -> copy contents of file1 to file2
cp file1 file2 file3 dir1 -> copy multiple files into directory
cp -r dir1 dir2 -> recursively copy the contents of dir1 to new directory dir2
cp -i file1 file2 -> interactive copy
cp -b file1 file2 -> this will create the backup of file1
cp -a
cp -s
cp -n file1 file2 -> it will not overwrite the contents of file2

mv -move
move the file from one directory to another directory or rename     -mv		- cut paste

-u	- update
-b	- backup
-n	-not overwritten and it will not show any prompt message
-i	-prompt message whether to overwrite or not
```


### mkdir

The mkdir(make directory) command allows users to create directories or folders.

```bash
# To create nested directories:
mkdir -p foo/bar/baz

# To create foo/bar and foo/baz directories:
mkdir -p foo/{bar,baz}

# To create the foo/bar, foo/baz, foo/baz/zip and foo/baz/zap directories:
mkdir -p foo/{bar,baz/{zip,zap}}

# Create specific directories:
mkdir path/to/directory1 path/to/directory2 ...

# Create specific directories and their [p]arents if needed:
mkdir -p path/to/directory1 path/to/directory2 ...

# Create directories with specific permissions:
mkdir -m rwxrw-r-- path/to/directory1 path/to/directory2 ..
```

### rmdir

The rmdir(remove directories) is used to remove _empty_ directories. Can be used to delete multiple empty directories as well. Safer to use compared to `rm -r FolderName`. This command can also be forced to delete non-empty directories.

```bash
# Outputs a message that the directory is being removed:
rmdir -v directory_name

# adding the -p option deletes the child directory then its parent directory:
rmdir -p directory_name

```

### rm

The rm(remove) command is used to remove objects such as files, directories, symbolic links etc from the file system.

```bash
# To remove all files and subdirs in <dir>:
rm -rf <dir>

# To ignore non-existent files:
rm -f <dir>

# Remove specific files:
rm path/to/file1 path/to/file2 ...

# Remove specific files [i]nteractively prompting before each removal:
rm -i path/to/file1 path/to/file2 ...

# Remove specific files printing info about each removal:
rm -v path/to/file1 path/to/file2 ...

# Remove specific files and directories [r]ecursively:
rm -r path/to/file_or_directory1 path/to/file_or_directory2 ...

# To remove all files and subdirs in <dir>:
rm -rf <dir>
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

### echo

```bash
# Print a text message. Note: quotes are optional:
echo "Hello World"

# Print a message with environment variables:
echo "My path is $PATH"

# Print a message without the trailing newline:
echo -n "Hello World"

# Append a message to the file:
echo "Hello World" >> file.txt

# Enable interpretation of backslash escapes (special characters):
echo -e "Column 1\tColumn 2"

# Default --> Disable interpretation of backslash escapes (special characters):
echo -E "Column 1\tColumn 2"
```

#### printf

```bash
printf
-> %d - int
-> %s -str
-> %f -float
-> %b -escape sequence
-> %c -Char
 printf "%d %s %f %b" 100 "ML" 20 "Hi all, \nWelcome to FP Training"

100 ML 20.000000 Hi all,
Welcome to FP Training

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

### Head  & tail
**Head**
Use the **`head`** command to truncate long outputs. The command can truncate files, for example:

```bash
head <filename>

head -n 5 bar.txt  # Prints the first ‘num’ lines
head -c 5 bar.txt    #  Prints the first ‘num’ bytes , Newline count as a single character
```

**Tail**
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


---

## Text Processing

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
grep -e "nagpur" -e "chennai" cities       # search for multiple patterns.

grep "^unix" geekfile.txt             # match the lines which start with the given string or pattern.

cat cities | grep "^m" :            # display line starts with m
grep "^[a-c]" cities                # display line starts with a,b,c

cat cities | grep "i$"              # display line ends with i     

cat cities | grep "ore$"            # display all lines end with ore


grep '[dp]' cities           # display line having letters d or p.

grep '[d-h]' cities          # display line having letters between d and h.

```

```bash
# finding file whose 3rd character is 'e'
 ls -1 | grep -E '^..[e].*' 
# To remove empty lines in a file
grep -v '^$' filename.txt > newfile.txt

# Show the employee records of all employees with employee Id between 8 and 19 (emp8 - emp19) including both
cat FILE | grep -E "^emp1([0-9]):|^emp([89]):"

^  - ends with
grep "^m" FILE

$ - ends with
grep -i "a$" FILE
```

### sed

SED command in UNIX stands for stream editor and it can perform lots of functions on file like searching, find and replace, insertion or deletion. By using SED you can edit files even without opening them

```bash
# sed
# A stream editor. Used to perform basic text transformations

# s` (substitute): This command is used to substitute one string with another string in a line.
sed 's/unix/linux/' FILE

# Replacing the nth occurrence of a pattern in a line
sed 's/unix/linux/2' FILE

# Replace the same string more than once per line (g flag)
sed 's/unix/linux/g' FILE

# Edit a file (adding -i flag), in-place; changes are made to the file(s).
# To replace all occurrences of "day" with "night" within <file>:
sed -i 's/day/night/g' FILE

# d (delete): This command is used to delete a line based on a pattern.
sed '/World/d' FILE

# i (insert): This command is used to insert text before a line.
sed 'i\Hello' FILE

# To insert a line before a matching pattern:
sed '/Once upon a time/i\Chapter 1'

# a (append): This command is used to append text after a line.
sed 'a\World' FILE

# To add a line after a matching pattern:
sed '/happily ever after/a\The end.'

# Multiple commands: You can specify multiple `sed` commands separated by semicolons (;).
echo "The cat chased the bird." | sed 's/cat/dog/ ; a\man'

```

```bash

# To remove leading spaces:
sed -i -r 's/^\s+//g' <file>

# To replace newlines in multiple lines:
sed ':a;N;$!ba;s/\n//g' <file>

# To remove empty lines in a file
sed -i '/^$/d' <file>
```



### tr

```bash

# Replace all occurrences of a character in a file, and print the result:
tr find_character replace_character < path/to/file

# Replace all occurrences of a character from another command's output:
echo text | tr find_character replace_character

# Map each character of the first set to the corresponding character of the second set:
tr 'abcd' 'jkmn' < path/to/file

# Delete all occurrences of the specified set of characters from the input:
tr -d 'input_characters' < path/to/file

# Compress a series of identical characters to a single character:
tr -s 'input_characters' < path/to/file

# Translate the contents of a file to upper-case:
tr "[:lower:]" "[:upper:]" < path/to/file
cat <file> | tr "[a-z]" "[A-Z]"

#  complement the sets using -c option
echo "my ID is 73535" | tr -cd [:digit:]

# Strip out non-printable characters from a file:
tr -cd "[:print:]" < path/to/file
```

### sort

```bash
# To sort a file:
sort <file>

# To sort a file by keeping only unique:
sort -u <file>

# To sort a file and reverse the result:
sort -r <file>

# To sort a file randomly:
sort -R <file>

# To sort a file and store the output in another file:
sort <inputFile> -o <outputFile>

# sorting a table on the basis of any column number by using -k option
sort -t':' -nk2 file.txt
```

### uniq

```bash
# To show all lines without duplication:
sort <file> | uniq

# To show not duplicated lines:
sort <file> | uniq -u

# To show duplicated lines only:
sort <file> | uniq -d

# To count all lines:
sort <file> | uniq -c

# To count not duplicated lines:
sort <file> | uniq -uc

# To count only duplicated lines:
sort <file> | uniq -dc
```


### wc

```bash
# To count the number of words (file or STDIN):

cat <file> | wc 
1st value - number of lines
2nd value - number of words
3rd value - number of bytes/character
In wc - space will be the default dilimiter.

wc -w <file>
cat <file> | wc -w

# To count the number of lines (file or STDIN):
wc -l <file>
cat <file> | wc -l

# To count the number of bytes (file or STDIN):
wc -c <file>
cat <file> | wc -c

# To count files and directories at a given location:
ls | wc -l
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

```bash
ls | grep "^[fd].*2$"
```

```bash
$ cat filw | sort | uniq -c | head -1
```

```bash
cat newemp | sed "/CustID/d" | sort -t "," -nk5 | cut -d "," -f 2,4 | head -1 
```

```bash
cat file1 2> efile
```