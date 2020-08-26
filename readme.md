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

![LInux Directories](/linux-directories.png?raw=true "Title")

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
11. Which - Locate command.12.
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
* Permissions       -rw-rw-r--
* Number of links   1
* Owner name        akhil
* Group name        users
* Number of bytes in the files 10400
* Last modification time Sep 27 08:52
* File name         sales.data

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
        cd -        Change to the previous directory.
        ```
    4. / Directory separator (forward slash).
    5. makdir [-p]  Create directory [p] is optional.
        ```
        mkdir new_dir
        ```
    6. rmdir - Remove a directory.( Only removes a directory that is empty)
    7. rm -rf directory - Recursively removes directory.