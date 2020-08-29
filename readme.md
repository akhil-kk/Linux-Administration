## Linux Administration

### Common directories

1. / - Root, the top of the file sysytme hierarchy
2. /bin - binaries and other executable programs.
3. /etc - sysytem configuration files.
4. /home - Home directories.
5. /opt - optional third party software.
6. /tmp - temporary space. cleared on reboot
7. /usr - user related programs.
8. /var - variable dtata, mostly log files.
9. /mnt Used to mount external file sysytems.
10. /proc - provides info about running processes.

**Directory Structure**

![Linux Directories](/notes/img/linux-directories.png?raw=true "Title")

## Shell - A program that accepts your commands and executes the commands.

* Shell is the default UI of alinux sysytem.
* Terminal gives acces to the shell.
* Command line is more powerfull

**root**

* Root is all powerfull
* Normal accounts can only do a subset of the things rot can do.
* Root access is typically restricted to sysytema administrators.
* Root is the superuser.

### Linux essential commands

**linux commands are case sensitive**

1. pwd - shows the current directory you are in.
2. cd - change directory, if cd is executed without any argument, it will take you to home directory.
3. ls - list all of the contents in alphabetical order.
4. ls -l  - long lisiting.
5. ls -p  - define file types when we list.
6. cat - concatenates and displays files.
7. echo - diplsays arguments to the screen.
8. man - displays the online manual , type "q" to quit man
9. exit - exits the shell
10. clear - clears the screen.
11. Which - Locate command.
12. tac - displays a file's content in reverse order.

eg: 

```
cd Downloads
cd ~     // home directory
ls -p
ls -l

```

**Decoding ls -l**

```
-rw-rw-r-- 1 akhil users 10400 Sep 27 08:52 sales.data
```
* Permissions                   -rw-rw-r--
* Number of links               1
* Owner name                    akhil
* Group name                    users
* Number of bytes in the files  10400
* Last modification time        Sep 27 08:52
* File name                     sales.data

* files or directories with a peroid or dot are considered as hidden files.
* Hidden files will not be displayed by ls.
* Use 
```
ls -a
ls -F   // get file types
        //  '/' means a direcctory
        // '@' means Link
        // '*' means Executable 

```

### Listing files by Time and in Reverse

```
ls -t   // List files by time
ls -r   // Reverse order
ls -latr // Long listing includes all files reverse sorted out by time.
ls -R   // Lists files recursively
ls - d  // List directory name, not contents.
ls --color  // colorize output
```

### Tree command

**Similar to ls -R, but creates visual output.**

```
tree -d         // List directories only
tree -c         // Colorize output
```

**Working with space in names**

* Just say no to spaces!
* ALternatives are
    * Hyphens(-)
    * Undercores(_)
    * CamelCase

## Environment Variables.
 
 * Storage location that has a name and a value.
 * Typically uppercase
 * Access the contents by executing:

 ```
 echo $VAR_NAME
 ```

 ## Directories.

 * Containers for other files and directories.
 * Provide a tree like structure.
 * Can be accessed by name or shortcut.

    **Directory shortcuts**
    1. . This directory
    2. .. The parent directory
    3. ```
        cd -      //Change to the previous directory.
        ```
    4. / Directory separator (forward slash).
    5. makdir [-p]  Create directory [p] is optional.
        ```
        mkdir new_dir
        ```
    6. rmdir - Remove a directory.( Only removes a directory that is empty)
    7. rm -rf directory - Recursively removes directory.

## File and Directory Permissions

**Permisions**
```
ls -l
-rw-rw-r-- 1 akhil users 10400 Sep 27 08:52 sales.data
```

```
Symbol      Type
'-'         Regular File
'd'         Directory
'|'         Symbolic Link

'r'         Read
'w'         Write
'x'         Execute
```

**Permission Categories**

```
Symbol      Category
'u'         User
'g'         Group
'o'         Other
'a'         All
```

'groups' command displays a users groups.

![Linux Directories](/notes/img/permissions.png?raw=true "Title")

### Changing Permissions

```
chmod       - Change mode command
ugoa        - User category user, group, other, all
+-=         - Add, substarct, or set permissions
rwx         - Read, write, Execute
```

eg

```
chmod a=r sales.data
chmod u=rwx, g=rx sales.data
```

### Changing Groups

* New files belong to your primary group.
* The 'chgrp' command chnages the group.

## Finding files and Directories

**Find Command**
```
find [path] [expression]    //recursively find files in path that match expression
-excec command {} \;        //run command against all the files that are found

find ./temp -iname *t       // '-i' ignore case, '*' matches all with t, 'find' looks for files or directories in temp
```

**Locate Command**

* fastre than find command.
* quries an index.

## Displaying Contents of Files

```
cat file        Display the contents of file
more file       Browse through a text file
less file       More features than more
head file       Output the begining portion of the file, displaye only 10 lines. 'tail -15 file' will get the last 15 lines
tail file       Output the ending portion of the file,displaye only 10 lines
```

### Nano Editor

* Nano is a simple editor.
* to open file 'nano filename'
* cntrl + o to save
* q to exit

### The Vi Editor

```
vi [file]           Edit file
vim [file]          same as vi, but more features
view [file]         Starts vim in read-only mode
```
####  Vi command Mode and Navigation

```
k           Up one line
j           Down one line
h           Left one character
l           Right one character
w           Right one word
b           left one word
^           Go to the begining of the line
$           Go to the end of the line.
x           Delete a character
dw          Delete a word
dd          Delete a line
yy          copy the current line
p           paste the text
u           undo
cntrl-R     redo
:w          Write changes to the file
:q          quit

```

![vim](/notes/img/vinav.png?raw=true "Title")

**Insert Mode**

```
i           Insert the cursor position
I           Insert at the beginning if the line
a           Append after the cursor position
A           Append at the end of the line
```
```
:set nu     Turn on line numbering
:set nonu   Turn off line numbering
```

**Modes**
```
Mode        Key
Command     Esc
Insert      i | a A
Line        :
```

## Graphical editors

1. emacs        Emacs has a graphocal mode too
2. gedit        The default text editor for Gnome
3. gvim         The graphical version of vim
4. kedit        The default text editor for the KDE

## File Operations

**Delete File**
```
rm file         Remove file
rm -r dir      Remove the diectory and its contents recursively
rm -f file      Force removal and never
```

**Copying Files**

```
cp source_file destinaion_file      //Copy source file to destination file.
cp src_flie1 [src_fileN...] dest_dir     //Copy source_files to destination_direction.
cpm -i          // Run in interactive mode
cp -r source directory destination         // Copy src_directory recursively to destination
```

**Moving and Renaming Files**

```
mv  source_destination
mv  -i source_destination
```
**sort**
```
sort file       //Sort text in file
sort -r         //Sort in reverse order
sort -u         //Sort unique (remove duplicate line)
sort -k F       //Sort by key. F is the field number
```

**Creating collectoin of files**

```
tar c|x|t f tarfile         // create a list of contents
```

**tar options**

```
c           Create a tar archive
x           Extract files from the archive
t           Display the tabke of contents list
v           Be verbose
z           Use compression
f file      Use this file
```

**Disk Usage**
```
du          Estimate file usage
du -k       Displays size in Kilobytes
du -h       Display sizes in human readable format
```
