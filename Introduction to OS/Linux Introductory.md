## Linux and Operating Systems


#### Module 1: History of Unix and Linux

##### Unix Operating Systems

First was born in Bell Labs in 1969 by *Ken Thompson* using Assembly language
*Dennus Ritchie* created C language
Then Unix OS in 1973 is rewritten in C

Unix has trademark problem and other companies created their own Unix systems
- IBM: AIX
- HP: HP-UX
- SUN: Solaris

Unix OS characteristics:
- Multitasking and time-sharing system
- Multi-users system
- Shell to interpret commands
- System config is stored as plain text files
- Everything is a file
- Combining many programs via *pipe*

Open source software:
- Open source means the source code is available
- Freedom to modify the source code
- Often under the GPL license

GPL (General Public License) created by *Richard Stallman*
First open source software: *emac*
GNU project in 1985 and it is not Unix, but Unix-like system
He is the founder of FSF (Free Software Foundation) in 1985

## Linux (the kernel)

Created by Linux Torvalds

## Linux Distributions

Companies providing technical support are called *Linux Distributors*

---

### Module 2: Login to the system

##### The Shell

A program used to interpret user commands
- sh (bourne shell)
- ksh (Korn shell)
- csh (C shell)
- bash (bourne again shell)
- zsh (extended bourne shell)

##### Connection Sessions

By default 7 sessions:
- 6 shell sessions
- 1 graphical session

Switching between sessions:
`CTRL + ALT + F<1,2,3,4,5,6,7>`

Shell session characteristic:
- `$` indicate that a logged user is simple with limited privileges
- `#` root user
- `~` home directory

4 possibilites to run commands:
- use command with parameter
- use command with option
- use command
- use command with parameter and option

Parameter is needed to run command while option is no needed

Running multiple command with `;`

Linux Commands

```bash
cd
sort ; ascii order
sort -n ; numerical order
cp
uname -a
ps -A
id
mkdir
cat
nano
touch
mv
ls
```

Shell shortcuts
```
CTRL + a : Cursor at the beginning of the line
CTRL + e : Cursor at the end of the line
CTRL + u : erase character until the beginning of the line
CTRL + l : erase character until the beginning of the screen
```

---

# Module 3: Files and Directories

Objectives:
- Copy files and directories
- Move and rename files and directories
- Create files and directories
- Remove files and directories
- Use symbolic links

```bash
mkdir
cd
pwd
rmdir ; must be empty directory
rm -r ; to remove directory recursively
cd - ; go previous directory
ls
cat
more
tail
head
```

## ls command

```bash
ls -i ; index node
ls -R ; recursive
ls -a ; hidden files
ls -l ; long list
```

## cp command

```bash
cp file1 dir1   ; copy file1 to directory dir1
cp file1 file2  ; copy file1 to file2
cp -r dir1 dir2 ; copy directory recusively to dir2
```

## rm command

```bash
rm -i  ; ask before removing
rm -rf ; recursive removing + force remove
```

## mv command

```bash
mv -i ; ask before overwriting
mv -f ; force overwriting
mv file1 file2
mv file1 dir1
mv dir1 dir2
```

## touch command

```bash
touch filename ; create empty file
; Modifies the data of the last access IF already exist and its content would not be lost
```

## cat command

```bash
cat [options] f1 f2 f3 ... fn
; CTRL+c to break
; CTRL+s to break with possibilty to resume
; CTRL+q to resume
```

## more command

```bash
more [options] f1 f2 f3 ... fn
; <SPACEBAR> display next screen
; <RETN> display next line
; <b> move one screen back
; /pattern search forward a pattern
; <n> find next occurance
; <h> help menu
; <q> quit
```

## head & tail commands

```bash
tail [options] f1 f2 f3 ... fn
; By default, display the last 10 lines
; -n option to display n lines

head ; similar to tail but from start
```

## wc command

```bash
wc -l ; line count
wc -w ; word count
wc -c ; byte count
wc -m ; character count
```

## File System Structure

One root: `/`
First level: directories under root
Second level: directories and files

## Paths to objects

Absolute path: `/user/share/......`
Relative path: `../../xxxxxxx`

## Symbolic Links

```bash
ln -s <source_file> <itslink>
```

---

# Module 4: Archiving and Compression

## Archiving

The process of grouping many objects in one file
Usually used as system backup or when moving data from one system to another
`tar` command is used
`jar` for archiving java packages

## Archiving: tar

Tape archiver

```bash
tar [options] archivename obj1 obj2 obj3 ... objn
-c ; create new tar archive
-t ; display list of files included in the archive
-x ; extract the archive
-f ; specifies archive name, default "/dev/rmt/0"
   ; if "-" then it reads from stdin
-v ; verbose mode
-l ; follows symbolic links
```

```bash
; Creation
tar -cvf archive.tar f1 f2 f3 dir1/ dir2/

; Extraction
tar -xvf archive.tar

; View
tar -tvf archive.tar
```

## Archiving: jar

For java classes

## Compressing: zip

Compressing files use less disk space and download faster than large, uncompressed files.

zip family:
- gzip/gunzip
- bzip2/bunzip2
- zip/unzip
- zcat
- gzcat

```bash
gzip -9 file ; -9 best compression rate
gzip -c file > file.txt.gz
```

bzip2/bunzip2
bzip2 takes longer time to compress but best compress rate

```bash
zip zipfilename f1 f2 f3 ; multiple file
```

Compression with tar/jar: just add `-z` for gzip, `-j` for bzip2

---

# Module 5: VI Editor

3 modes:
- command mode
- insert (edit) mode
- last line mode

## Command mode

only understand commands
cut, copy, paste, save
Commands are case sensitive

## Edit mode

Switching to it, press `i`
Switch back to command mode, press `esc`

Commands to switch to edit mode
- `i`: insert before cursor
- `I` insert beginning of the line
- `a` append after cursor
- `A` append end of line
- `o` new line below cursor
- `O` new line above cursor

## command mode commands

- h, backspace, move left one character
- l, spacebar, move right one character
- j, move down one line
- k, move up one line
- w, forward one word
- b, backward one word
- e, end of current word
- $, end of current line
- 0, beginning of the line
- ^, first non whitespace character
- ret, new line
- G, last line of file
- R, overwrite characters from cursor onward
- r, replace character
- D, delete contents of line after the cursor
- C, delete contents of a line after the cursor and insert new text
- dd, delete line
- dw, delete word
- cw, change word
- x, delete character
- s, substitute one character
- S, substitute entire line
- u, undo last change
- U, undo all changes to the entire line
- `:n,nd`, delete line n through n
- `.`, repeat previous command

- :w
- :w filename
- :wq or :x
- :q
- :q!

## Moving between vi modes

- Command to Edit
	- i a o
- Edit to Command
	- ESC
- Command to Last line
	- : / ?
- Last line to Command
	- Return

---

# Module 6: File Permissions

Objectives:
- Default permissions
- View file and directory permissions
- Determine file or directory access
- Change permissions

Linux authorization divided into two levels:
- Ownership
- Permission

## Ownership of Linux Files

Ownership has 3 types:
- User (Owner)
- Group
- Other (permission for the world)

Permissions = user behaviour

Permissions:
- r (4)
- w (2)
- x (1)

To view the permission: `ls -l`

## Changing Permissions (chmod)

Way of using this command:
- Symbolic mode
- Absolute (numeric) mode

```txt
chmod symbolic_mode filename

symbolic_mode: [who op permission]

symbolic_mode:
- u user
- g group
- o other
- a all

op:
- +
- -
- =

permissions:
- r
- w
- x
```

```bash
; Examples

chmod g=rwx,u=rwx,o=r ; rwxrwxr--
chmod g+x,u+r,o-wx ; rwxrwxr--
```

### Absoulute Mode

- 7 (rwx)
- 6 (rw-)
- 5 (r-x)
- 4 (r--)
- 3 (-wx)
- 2 (-w-)
- 1 (--x)
- 0 (---)

## umask utility

Default permission for files `rw-rw-rw`
Default permission for directories `rwxrwxrwx`
User file-creation mode mask (umak) is to determine the file permission for newly created files

## Change Ownerships (chown)

## Change Group ownership (chgrp)

