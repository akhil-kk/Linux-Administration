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
**Cut options**I

* -d delimeter        Use delimeter as filed seperator.
* -f N                Display the Nth field








