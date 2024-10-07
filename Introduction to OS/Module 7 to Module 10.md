### Module 7: Input/Output and Pipes

**Objectives**
- Redirect outputs to files
- Read inputs from files
- Pass outputs to another command

**Redirection** is a feature in Linux that you can change the standard input/output devices.

- `<` read the input from a file instead of the keyboard (input redirection)
- `>` write the output to a file instead of the screen (output redirection)
- `>>` append the output
- `2>` write the error outputs to a file
- `2>>` append to the output

Redirect standard output not just to a files, but also devices
```
cat music.mp3 > /dev/audio
```

|  File  | File Descriptor |
|:------:|:---------------:|
| STDIN  |        0        |
| STDOUT |        1        |
| STDERR |        2        |

In Linux/Unix, everything is a file. And every file has an associated number called File Descriptor (FD).

**Redirecting Errors**

```
myprogram 2> error.file
```

##### Translate (tr) command

Used to translate one character or group of characters in the inputs and shows the result on the stdout.
The command is interactive and starts running when you press enter.
But you can use the < or > to redirect input/output

```bash
tr ' ' '\t'
tr '\n' ' ' < file.txt
tr -d ' ' < file.txt
tr 'a-z' 'A-Z' < my-text.txt
```

##### Pipes: the character ' | '

The Pipe is a command that lets you use two or more commands.

```bash
cat filename | less # pipe the output of the cat command to less
ls -l | more # display page per page the content of the current directory
ls | sort # display a sorted list of the content 
find . -type f | less # display page per page from the find command's outputs
man cat | mail -s "manual"
```

##### Tee: command and pipes

Making a copy of passed outputs to a new file
The pipe action would not be stopped.

```bash
ls -l | tee ls.out | more
```

##### Extended Arguments: xargs

*xargs* is a command for building an execution pipeline from standard input.

Using *xargs* allows tools like echo and rm and mkdir to accept standard input as arguments.

```bash
echo 'one two three' | xargs mkdir
```

##### *xargs* Command and Pipes

```bash
ls | xargs cat # passing the content of ls as arguments to cat
```

```bash
find /etc/ -name passwd | xargs ls -l
```

---

### Module 8: Shell Bash

**Objectives**
- Shell metacharacters
	- Pathname
	- Substitution
	- Quoting
	- Command Redirection
- Command history
- Initialization files
- Bash Variables

##### Introduction

Boune Again SHell (bash), released in 1989.
- Shell bash is a binary file in `/bin`
- Shell is commands interpreter.
- Shell is executed after user connection
- Shell exits after user logout

Object Names
- Each object (file or directory) has a name
- Avoid using special characters name
- Each space or special character should be preceded by '\\'

| Metacharacter | Purpose                           | Example     |
| ------------- | --------------------------------- | ----------- |
| \*            | Matches zero or more char         | a\*         |
| \?            | Matches only one char             | patter?     |
| \[xyz\]       | Matches one char from the set     | patter\[xyz\] |
| \[\^xyz\]     | Matches one chat not from the set | patter\[\^xyz\]            |

##### Shell Variables

Use **set** and **env** commands to display all/some shell variables.
Each variable stores one information to be used by the shell/user

Examples:
- PATH: paths to all executable files
- PS2: specific character to continue a command in the next line
- PPID: shell parent process PID

*echo* to display a variable content `echo $PS2`
To create a new variable run: `variable_name=value`
To make a variable visible to shells run: `export variable_name`

##### The Tilde Character \~

Replace the path to my directory `cd ~`
Replace the path to the directory of another user `cd ~/user/mail`

##### Tabulation (Tab) key

Autocomplete names within commands:
- Command names
- Files and directory names

##### The Special Character \$

Used to reference variables' contents: `$HOME, $PS1, ...`

Arithmetic Expansion
```bash
# $((expression))
echo $((2+2))
echo $(($((5**2))*3))
echo Five times five equals $((5*5))
```

##### The Backquote Character \`

Call a command within another command.

```bash
echo "current date is: `date`"
echo "My machine name is: `hostname`"
```

##### The Special Character \{\}

With **brace expansion**, you can create multiple text strings from a pattern containing braces.
Used to compose objects' names

```bash
echo Front-{A,B,C}-Back
echo Number_{1..5}
echo {Z..A}
ls access.{db,deb}
cp source.{cpp,c,h} $HOME/backup/
```

##### The Escaping Character \\

Called backslash (escaping character)

The **escape** (\\) preceding a **character** tells the **shell** to interpret that **character** literally.

```bash
echo "100\$"
```

##### Quoting \' and \"

**Single quotes**
- Single quotes are used to produce a string as it is.
- If we need to suppress *all* expansions, use single quotes.
- **echo** 'this text would not show the date: \`date\`'

**Double quotes**
- If you place text inside double quotes, all the special characters used by the shell lose their special meaning and are treated as ordinary characters
- The exceptions are "$", "\\" and " \` "

This means that word-splitting, *pathname expansion*, *tilde expansion* and *brace expansion* are suppressed. But *parameter expansion*, *arithmetic expansion* and *command substitution* are still carried out.

##### History of Commands

Each user has its own directory `/home/user`
All executed commands are stored in `.bash_history` hidden file within its own directory.
- The file **.bash_history** size is controlled with env_var **HISTSIZE**
- Use `history` command to display all the history
- Use `CTRL + r` to search within the history
- Use `CTRL+ c` to exit the search

##### User Login Process

User login to the system: if login/password accepted, then a shell program is executed.
- Read the global profile `/etc/profile`
- Read the local profile `~/.bash_profile`
- Read again the local profile `~/.bashrc`

##### /etc/profile

It is a script file executed by the shell during the login process.
This is used to define a global profile for all users.
Setting of the most used environment variables PATH, USER, LOGNAME, MAIL, HOSTNAME, HISTSIZE, INPUTRC

##### \~/.bash_profile and \~/.bashrc

Each user has its own files.
Each user can change its environment using those files
- New variable
- Command alias
- umask command

##### \~/.bash_logout

A script file executed when the user logout.
Used for automating some tasks such as backup, deleting temporary files.

##### Command alisases

**alias** is a new name of an exiting command
Use **alias command** to display all already defined command aliases

```bash
alias new_name='existing command'
```

---

### Module 9: Searching Files with Contents

**Objectives**
- Module introduces searching files and directories
- Search with **grep**, **egrep** and **fgrip** commands
- Locate a file or directory using the **find** command

##### GREP

- GREP (Global Regular Expressions Print)
- Scans for a pattern in file or files
- A pattern is an expression that specifies a set of strings by interpreting characters as meta-characters.
- Asterisk meta-character (\*)  is interpreted as meaning "zero or more"
- This enables users to type a short series of characters and meta characters into a grep command to have the computer show us what lines in which files match.

##### GREP Options

```text
grep -[options] target
-i : case insensitive
-l : list only names of files with matching lines
-n : precedes each line with the relative line number in file
-v : invert the search
-C : counts the lines that contains the pattern
-w : searches for the expression as a complete word, ignoring those matches that are substring of larger words
```

##### Regular Expressions

A Regular Expression is a sequence of characters that define a search pattern.
- ? : the preceding item optional and matches at most once
- \* : the preceding item will be matched zero or more times
- \+ : the preceding item will be matched one or more times
- {n} : the preceding item will be matched exactly n times
- {n,} : the preceding item will be matched at n or more times
- {,m} : the preceding item will be matched at most m times
- {n,m} : the preceding item will be matched at least n and at most m times

```text
grep meta-character
^ : beginning of the line
$ : end of line
. : matches one
* : zero or more times
[xyz] : matches one char from xyz
[^] : matches one not in the pattern
[a]{n} : matches "a" character exactly n times
```

##### EGREP 

- EGREP (Extended Regular Expression Print)
- Additional meta-character
- egrep equals to `grep -E`

```text
+     : matches one or more of the preceding char
?     : matches zero or one char
x|y   : matches either x or z
(x|y) : groups of char [ '(1|2)+' matches one or more 1 or 2 ]
<     : beginning of the word [ '<test' match all word begins with test ]
>     : end of word
```

- `c` any non special char
- \c turn off any special meaning  of character c

##### FGREP

- Faster version of grep
- Does not support Regular Expression
- fgrep is equal to grep -F

##### Find command

Find a file, who's name ends with .bar, within the current directory and only search 2 directories deep.

```bash
find . -name *.bar -maxdepth 2 -print
```

Search for files owned by the user "joebob"

```bash
find / -user joebob -print
```

```bash
find / -type l -print
```

---

### Module 10:  Searching for Files and Directory

**Syntax**: find pathname expression \[action\]

**Pathname**: the absolute or relative path where the search originates.

**Expression**: the search criteria specified by one or more options. Specifying multiple options causes the find command to use the Boolean operator "and" so all listed expression must be true.

**Action**: the action required after the files have been located. The default action is to print all pathnames matching the criteria to the screen.

|    Expression     |                                         Definition                                         |
|:-----------------:|:------------------------------------------------------------------------------------------:|
|  -name filename   |      Find files matching the specified filename. Metacharacter must enclosed with ""       |
| -size \[\+\|\-\]n |              Find files that are larger than +n, smaller than -n or exactly n              |
| -atime\[\+\|\-\]n | Find files that have been accessed more than +n days, less than -n days, or exactly n days |
| -mtime\[\+\|\-\]n | Find files that have been modified more than +n days, less than -n days, or exactly n days |
|   -user loginID   |                       Find all files that are owned by loginID name                        |
|       -type       |          Find a file type, for example f(file) or d (directory) l (symbolic link)          |
|  -newer filename  |                  Returned files were modified more recently than filename                  |
|       -perm       |                       Find files with certain access permission bits                       |

|        Action        |                        Definition                        |
|:--------------------:|:--------------------------------------------------------:|
| -exec command {} \\; |                   Run specific command                   |
|  -ok command {} \\;  | Require confirmation before the find applies the command |
|        -print        |       Print the filename to screen. Default action       |
|         -ls          | Display the current path name and associated statistics. |

```bash
find . -name output.txt
find . -name '*.txt'
find . -type d
find / -size 1000k
find /var/ftp/ -perm -777
find /var/ftp/ -type f -exec ls -l {} \;
find /var/ftp/ -perm 777 -exec chmod go-w {} \;
```

```bash
find . -perm -500
find . -perm -500 -name "dir*"
find . -name "*.txt" | xargs ls -l
find . -name "?.txt" | xargs ls -l
find $HOME/3162 -mtime +30 -name "*.txt"
find $HOME/3162 -mtime -30 -name "*.txt" | xargs ls -l
find . -newer 3162/output.txt -name "*.txt" | xargs ls -l
```

