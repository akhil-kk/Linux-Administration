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



