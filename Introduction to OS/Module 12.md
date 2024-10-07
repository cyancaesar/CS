### Module 12: Shell Scripting

**Shell** is a program that acts as interface between the user and the Linux system.

It allows the user to enter commands for the OS to execute.

##### Creating a Script

Shell can be used as a programming language to write scripts that can perform specific tasks.

There are two ways of writing shell scripts:
- Typing a sequence of commands, allowing the shell to execute them interactively.
- Storing those commands in a file (using any text editor) that can be then invoked as a program.

```bash
# Variables

var1=Hello
echo $var1

var2="Hello Shell"
echo $var2

read var3
echo $var3
exit 0
```

- Variables are stored as strings
- Variables are case sensitive
- The contents of a variable can be accessed by preceding its name with $
- User input can be assigned to a variable using the read command

```bash
# Parameter Variables

echo "The program $0 is now running"
echo "The first parameter $1"
echo "The second parameter $2"
echo "The parameter list $*"
exit 0
```

```bash
# Special Variables

# ($#) Returns the number of parameter passed

echo My name is $0
[ $# -gt 0 ] && echo "First parameter $1"
[ $# -gt 1 ] && echo "Second parameter $2"

# ($@) Returns all the parameters passed to the command
```

##### Conditions (if-else)

```bash
# [ condition ]

# str1  = str2
# str2 != str2

# expr1 -eq expr2
# expr1 -ne expr2
# expr1 -gt expr2
# expr1 -ge expr2
# expr1 -lt expr2
# expr1 -le expr2
# ! expr1

if [ condition ]
then
	statement
elif [ condition ]; then
	statement
else
	statement
fi
```

##### Repetitions (loop for)

```bash
for iterator in 1 2 3 hello here
do
	echo $iterator
done

for file in $(ls f*); do
	touch $file
done
```

##### Repetitions (loop while)

```bash
echo "Enter a word"
read word

while [ $word != "secret" ]
do
	echo "Wrong word."
	read word
done
```

##### Case statement

```bash
# Used mostly for initiation scripts

case "$1" in
'sun')
	echo "hot";;
'cloudy')
	echo "cold";;
esac
```

```bash
echo "Is it morning?"
read tod

case "$tod" in
	yes ) echo "GM";;
	no ) echo "GA";;
	* ) echo "Answer not recognized";;
esac

case "$tod" in
	yes | y | YES | Yes ) echo "GM";;
	n* | N* ) echo "GA";;
esac
```

##### test command

**test** is used as part of the conditional execution of **shell commands**.
**test** exits with the status determined by EXPRESSION
Placing \[ \] is same as testing with **test** command

```bash
test s
test -n string
test string1 = string2
test string1 != string2
...
```

```bash
# deleting a file and ensuring it is exists
test -f /path/to/file && rm -f /path/to/file 

# creating a directory only if it is not exist
test -d /directory || mkdir /directory
[ -d /directory ] || mkdir /directory
```

##### Functions

```bash
foo() {
	echo "bar"
}
foo
```

```bash
func() {
	statement
}

# or

function func {
	statement
}
```

```bash
func() {
	echo Hello $1
	return 5
}

func World
echo "Previous function return $?"
```