## Linux Intermediate skills

### Wild Cards

* A character or a string used for pattern matching.
* Wildcards can be used with most commands.
    * ls
    * rm
    * cp

**'*' Matches zero or more characters**
eg:
```
*.txt
a*
a*.txt
```

**'?'Matches exactly one character**

```
?.txt
a?
a?.txt
```
 
**[] A character class**
Matches any of the characters included between the brackets. Matches exactly one character.

* [aeiou]
* ca[nt]*

**[!]**
Matches any of the characters not included between the brackets. Matches exactly one character.
* [!aeiou]*
* [a-g]*
* [3-6]*

**Named Character classes**

* [[:alpha]]  matches alphabets
* [[:alnum]]  matches aplha numeric digits
* [[:digit]]  matches digits
* [[:lower]]  matches lower case letters
* [[:space]]  matches white space
* [[:upper]]  matches uppercas letters
* \ - escape character

## Input/Output Types

```
I/o Name        Abbreviation        File Description

Standard Input  stdin               0
Standard Output stdout              1
Standard Error  stderr              2
```

**Redirection**

* '>' Redirecs standard output to a file. Overwrites (truncating) existing contents
* '>>' Redirects standard output to a file. Appends to nay existing contents
* '<' Redirects input from a file to a command.
* '2>file' Redirects standard error to a file.

**Compare files**

```
diff file1 file2            //compare two files
sdiff file1 file2           //sid by side comparison
vimdiff file1 file2         //Highlight differences in vim
```

**Search contents in a file**

* grep      Diplay lines matching pattern.

```
grep pattern file
```
* grep options

-i Perform a seacrh ignoring case
-c Count the number of occurances in a file.
-n Precede output with line numbers.
-v Invert Match. Print lines that dont match.

**Pipe**

* pipe '|' chains two commands.
* Takes the standard output from the preceding command and passes it as the standard input to the following command.
* Error messgaes from the first command will not be passed to second command by default.

```
cat file | grep pattern
```
**cut command**

```
cut [file]          //Cut out selected portions of file. If file is omitted, use standard input.
```
**Cut options**

* -d delimeter        Use delimeter as filed seperator.
* -f N                Display the Nth field

## Copy files over network

* To copy files from llocal work station to a linux server or between linux servers we need to use 'SCP' or 'SFTP'.

SCP - Secure copy
SFTP - SSH file transfer protocol

To use scp or sftp we need a client like 'PuTTY secure file transfer client'.

Graphical SCP/SFTP clients

* cyberduck
* fileZilla
* WinSCP

eg:
```
scp source destination copy source to destination
eg: scp abc.txt linuxsvr:/tmp/

sftp host           start a secure file transfer session with host. (when connected to a remote, use lls oand lpwd for lisiting files)

ftp host            start a file transfer session with host.
```

## Environment variables

*  Environment variable is a storage loation that has a name and a value. They often affect the way programs behave.To view all environment variables 

```
printenv
```

* linux environment variables are case sensitive.

* to create env variables 
```
export VAR="value"
```
* To remove env variables
```
unset VAR
```

## Processes and Job control
```
ps              display process status
ps -e           display all proesses
ps -ef          display all processes, full
ps -eH          display a process tree
ps -e --forest  display a process tree
ps -u username  display user's processes.   
 ```

**Background and Foreground process**

```
command &   Start comand in background
ctrl-c      Kill the foreground process
ctrl-z      Susupend the foreground process
kill 123    kill a process by process id
```
## Repeated jobs with Cron

![crone](/crone.png?raw=true "Title")

```
crontab file        install new crontab from file
crontab -l          list your crone jobs
crontab -e          Edit your crone jobs
crontab -r          Remove all of your cron jobs
```
## Switching users 
```
whoami                  returns your current account name
sudo -u root command    same as above
sudo -u user command    run as user
```

## Shell History

```
history     Displaye shell history
HISTSIZE    Controls the number of commands to retain in history
export HISTSIZE = 1000
```

## installing softwares

**for RPM packages**
```
yum search string           Search for string
yum info [package]          Display info
yum install [-y] package    install package
yum remove package          Remove package
rpm -qa                     List all installed packages
rpm -ivh package.rpm        install package
rpm -e package              remove
```

**DEB ditributions**

APT - advanced Packaging tool
```
apt-cache search string         Search string
apt-cache show package          display info
apt-get install [-y] package    Install package
apt-get remove package          Remove package , configuration changes stay
apt-get purge package           Remove package, deleting configuration
dpkg -l                         List installed packages
dpkg -i                         install package














 











