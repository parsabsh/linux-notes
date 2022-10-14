# Introduction

Linux is an open-source Unix-like operating system based on the Linux kernel, an operating system kernel first released on September 17, 1991, by Linus Torvalds. Linux is typically packaged as a Linux distribution.

## Linux Distributions ("Distro"s)

Linux is one of the most popular operating systems, with around 3-3.5 billion users worldwide. Thanks to its extensibility and nature as an open-source, it has led to the creation of many Linux-based distributions that have strong features.

### The most popular linux distributions

![reddit](https://preview.redd.it/80so7f9nna751.png?width=960&crop=smart&auto=webp&s=0d394083088dd9cc1e36868b99527779d0241d02)

You can find a complete tree of linux distros [here](https://upload.wikimedia.org/wikipedia/commons/b/b5/Linux_Distribution_Timeline_21_10_2021.svg)

## What are "shell" and "terminal" ?

### **Shell**

Shell is an interface that connects you to the operating system (OS) and lets you work with it. Shell is responsible for interpreting commands and return the results back. The default shell in ubuntu (and many other distros) is _**bash**_.

### **Terminal**

Terminal is a graphical software that you can access any shell you want through it.
![image](https://user-images.githubusercontent.com/92635013/195100325-217ca755-2767-470c-995d-fbf9fa89c065.png)

## General Structure of Linux Commands

```bash
COMMAND [OPTIONS] [ARGUMENTS]
```

- **COMMAND:** This part is the command that is sent to the OS. Every command is a program that tells the OS to do something.
- **OPTIONS:** We can put zero or more options here. They specify the details of our command. Options are denoted by **_"-"_** or **_"--"_** sign.
- **ARGUMENTS:** These are the inputs that the command is going to operate on.

**Be aware:** All of above parts are case sensitive.

**Help:** You can get information about a command, using one of the following commands:

```bash
COMMAND --help
```

or

```bash
man COMMAND
```

## Some Useful Ubuntu Shortcuts

_**Note**_: Super key is the key with windows sign on it (= Windows key).
|Key|Action|
|:--|:-----|
|Super key|Opens Activities search|
|Ctrl + Alt + T|Ubuntu terminal shortcut|
|Super + L or Ctrl + Alt + L|Locks the screen|
|Super + D or Ctrl + Alt + D|Show desktop|
|Super + A|Shows the application menu|
|Super + Tab or Alt + Tab|Switch between running applications|
|Super + Arrow keys|Snap windows|
|Super + M|Toggle notification tray|
|Super + Space|Change input keyboard (for multilingual setup)|
|Alt + F2|Run console|
|Ctrl + Q|Close an application window|
|Ctrl + Alt + arrow|Move between workspaces|
|Ctrl + Alt + Del|Log out|

# 1) Basic Commands

## echo

```bash
echo <argument>
```

The simplest command in linux is `echo` which simply prints out every argument that is passed to it. Try typing `echo hello linux!` in your terminal!

## pwd

```bash
pwd
```

In linux, a **directory** is something that contains some other files and directories. When you open the _terminal_, you are in `/home/<username>` by default (where `<username>` is your account name).

By entering `pwd` in your terminal (which stands for `print work directory`), you can see where you are in the file system.

## cd

```bash
cd <address>
```

`cd` stands for `change directory` and as its name implies, we can use it to move in the file system.
(`<address>` can be either relative or absolute)

**~** : This sign stands for the current user's home directory which is `/home/<username>`. For example `cd ~/Downloads/` will move me to `/home/parsa/Downloads/`.

## ls

```bash
ls [OPTIONS]... [FILE]...
```

This command, lists information about the FILEs (We often use this command without any arguments which takes the current directory as argument by default)

### important options

|option  |effect  |
|:-------|:-------|
|-a or --all|do not ignore entries starting with .|
|-l|use a long listing format (in more details)|
|-h or --human-readable|with -l and -s, print sizes like 1K 234M 2G etc.|
|-r or --reverse|reverse order while sorting|
|-t|sort by time, newest first|

## history

```bash
history [<number of commands>]
```

If we enter `history` in terminal, we can see the complete history of our entered commands. We can also restrict the number of commands to see. For instance, by entering `history 3`, we can see our last 3 commands.

Moreover, we are able to clear our history using `history -c` command.

## mkdir

# 4) Scripting

A **bash script** is a file that we run a set of processes by executing it.

**_Shebang:_** A shebang is a line at the beginning of the script (or every executable file). We use it to tell the OS how to interpret this file. This line consists of **`#!`** followed by the address of desired interpreter. For example, the shebang we should use at the beginnig of a bash script file is `#! /bin/bash`.

## Variables

We can define variables in bash scripts just like other languages. For instance:

```bash
#! /bin/bash
name=parsa
echo "hello $name"
```

Output: `hello parsa`

We can access the arguments passed to our script using `$n` which will give us the nth argument if it exists and "" if it doesn't. (If n has more than one digit, we have to use `${n}`) For example:

If our script file `hello.sh` is:

```bash
#! /bin/bash
echo "$1 says hello to $2"
```

the output will be:

```shell
$ ./hello.sh parsa mahyar
parsa says hello to mahyar
```

There are some special variables in bash scripts:
|Variable |Value |
|:--------|:-----|
|$0|The filename of the current script.|
|$1-$9|Stores the names of the first 9 arguments or can be used as the arguments’ positions.|
|$$|The process id of the current shell.|
|$#|The number of arguments supplied to a script.|
|$*|Stores all the command line arguments by joining them together.|
|$@|Stores the list of arguments as an array.|
|$?|Specifies the exit status of the last command or the most recent execution process.|
|$!|Shows the id of the last background command.|
|$-|Shows the options set used in the current bash shell.|

Example:

```bash
#! /bin/bash

# sample.sh

echo "Process id of shell = $$"
echo "Name of shell script = $0"
echo "Number of args = $#"
echo "Argument 1 = $1"
echo "Argument 2 = $2"
```

Output:

```shell
$ ./sample.sh 1 2 3
process id of shell = 22342
Name of shell script = ./sample.sh
Number of args = 3
Argument 1 = 1
Argument 2 = 2
```

We can use the output of a command in another command. For instance:

```shell
$ ./hello.sh $(whoami) mahyar
parsa says hello to mahyar
```

## Arrays

We can define arrays in two ways:

1) Evaluate inline:
  
   ```bash
   my_array=(1 "parsa" 56 'h')
   ```
  
   **hint:** variables in an array should not be the same type.

2) Create an empty array:
  
   ```bash
   declare -a my_array
   ```

### Append

We can append one or more elements to an array like this:

```bash
my_array += (23)
my_array += ("ali" "sara" 174)
```

### Access Elements

We can access all elements in our array like this:

```bash
echo ${my_array[@]}   # print the whole array
echo ${my_array[*]}   # print the whole array
```

We can also access the element in a specific index like this:

```bash
echo ${my_array[0]}   # arrays start at 0
echo ${my_array[1]}
echo ${my_array[-1]}  # you can use negetive index to index from the end

my_array[0]=hello     # you can change an index value
my_array[10]='new'    # accessing an "out of range" index would result in an append!
```

Moreover, to access the length of an array use `#`. For example:

```bash
echo "the array contains ${#my_array[@]} elements"
```

To access the indices of our array use `!`. Like this:

```bash
echo "${!my_array[@]}"
```

Also, we can use `unset` command to remove an index from our array:

```bash
a1=(1 2 3 4 5 6 7)
unset a1[1]
unset a1[3]
echo ${!a1[@]}          # index 1 and 3 are removed
echo ${#a1[@]}          # arrays size is decreased by 2
echo ${a1[@]}           # the values of those indices are lost too
```

and the output will be:

```shell
$ ./hello.sh
0 2 4 5 6
5
1 3 5 6 7
```

## Hashmaps

Hashmaps are just like arrays and we can use the scripts that we have written for arrays, for hashmaps too.

The only difference between arrays and hashmaps is the way they're defined:

```bash
declare -A fruits

fruits=([pineapple]=10 [banana]=3 [apple]=2)
fruits+=([potato]=1 [mango]=12 [apple]=3)

echo ${!fruits[@]}          # keys
echo ${fruits[@]}           # values
# notice that "apple" key appears once even though we defined it twice
# notice that the index orders are different from how we inserted them
echo ${#fruits[@]}
```

## Conditional Statements

### if-then

The simplest conditional statement in bash is `if-then` statement:

```bash
if command
then
   commands
fi
```

or in this format:

```bash
if command; then
   commands
fi
```

**Note:** There is a subtle difference between if statements in bash and other languages. In other languages, the conditional term is either True of False. But in bash, it's a command. If the command is executed successfully (with exit code `0`), then the `commands` will be executed (and otherwise, they won't).

### if-then-else

Another conditional structure in bash is `if-then-else` statements:

```bash
if command
then
   commands
else
   commands
fi
```

or in this format:

```bash
if command; then
   commands
else
   commands
fi
```

### if-elif-else

The `if-elif-else` statements are in the following format:

```bash
if command-1; then
   commands-1
elif command-2; then
   commands-2
...
elif command-n; then
   commands-n
else (optional)
   commands-else
fi
```

Note that the `else` part is optional.

### switch-case

Another useful conditional statement in bash is `switch-case` structure:

```bash
case EXPRESSION in

   PATTERN_1)
      STATEMENTS
      ;;

   PATTERN_2)
      STATEMENTS
      ;;

   PATTERN_N)
      STATEMENTS
      ;;

   *)
      STATEMENTS
      ;;
esac
```

### test command

Earlier we talked about the difference between bash and other languages in conditional term.

Now if we want to use the `True/False` structure for `if-statements`, linux has provided us with a useful tool which returns `exit code 0` if `True`, and `exit code 1` if `False`. This tool is the `test` command.

```bash
test conditions
```

or

```bash
[ conditions ]
```

Using the `test` command, you can have `Numeric Comparisons`, `String Comparisons`, and `File Comparisons`. There are a lot of options built into the `test` command, that I strongly suggest you to use the following command for more information:

```shell
$ man test
```

**ٔNote:** You can also use AND(`&&`) and OR(`||`) operations to combine conditions in `test` command.

## Loops

Using loops, we can repeat a piece of script.

### For Loops

The first loop structure is `for loop`. we can use it like this:

```bash
for variable in list
do
    commands
done
```

`list` is something that contains some elements. There are different ways to determine a list in a for loop:

- manually:
  
   ```bash
   #! /bin/bash
   for word in "linux" "is" "perfect" "and" "windows?" "mmm," "not" "bad."
   do
      echo -n "\$word "
   done
   echo
   ```

   **Note:** The `"` character is optional unless the elements have special characters like `'`, `space`, etc.
- read from a file:

   ```bash
   #! /bin/bash
   for word in \$(cat list.txt)
   do
      echo \$word
   done
   ```

- read from a folder:

   ```bash
   #! /bin/bash
   for word in $(pwd)/folder/*
   do
      if [ -d \$word ]; then
         echo "\$word is a folder"
      elif [ -f \$word ]; then
         echo "\$word is a file"
      fi
   done
   ```

- use a counter variable:

   ```bash
   #! /bin/bash
   for (( i = 1; i <= 10; i++ ))
   do
      echo "Round \$i"
   done
   ```

   We can use `{1..10}` as a list to make the same loop as the above example.

### While Loops

Using a `while loop` we can repeat executing some commands as far as a condition is true. This is the general structure:

```bash
while command
do
    commands
done
```

Example:

```bash
#! /bin/bash
var=10
while [ \$var -gt 0 ]
do
   echo "Round \$var"
   ((var--))
done
```

**Note:** We can use `break` and `continue` statements just like every other language.

## Options and Arguments

In this rather short section, we want to work with any number of arguments and options.

First you should get to know the `shift` command. As its name implies, it _shifts_ the arguments to the left by 1. This means that the first argument (`$1`) will be removed (and will be replaced by the second one (`$2`)).

Now we can combine `while loop` and `shift` command to work with an arbitrary number of arguments. See this example:

```bash
#!/bin/bash
count=1
while [ -n "\$1" ]  # continues until there is no arguments
do
   echo "Parameter #\$count = \$1"
   ((count++))
   shift
done
```

Now we can work with options by combining `while loop`, `switch-case statement`, and `shift operator`. Consider the following example:

```bash
#! /bin/bash
OPTION1=false # Boolean Option with default value
OPTION2=hello # Parameter Option with default value

while [ -n "\$1" ]
do
   case "\$1" in
      -o1) echo "OPTION1 entered"
         OPTION1=true
         shift ;;

      -o2 | --option2) echo "OPTION2 entered"
         if [ -z \$2 ]; then
            echo "Option2 needs a parameter"
            exit 1
         fi
         OPTION2=\$2
         shift
         shift ;;

      --) shift
         break ;;

      *) echo "\$1 is not an Option"
         exit 1 ;;
   esac
done

echo "Option1: \$OPTION1, Option2: \$OPTION2"
count=1
while [ -n "\$1" ]
do
   echo "Parameter \$count = \$1"
   count=\$[ \$count + 1 ]
   shift
done
```

And the output will be:

```shell
$ bash options.sh -o1 --option2 bye -- Parsa Reza Amir
OPTION1 entered
OPTION2 entered
Option1: true, Option2: bye
Parameter 1 = Parsa
Parameter 2 = Reza
Parameter 3 = Amir
```

<details>
<summary><b>Another Example: How's the weather?</b></summary>

In this example we write a script to get the weather of a region that is passed to script as an argument. We also write a `--help` option for it :)

```bash
#! /bin/bash

case $1 in
   -h | --help)
      echo "Short Option   Long Option    Description"
      echo "-h             --help         Show help"
      echo "-l             --location     Show weather"
   -l | --location)
      curl https://wttr.in/$2
      ;;
   *)
      curl https://wttr.in
      ;;
esac
```

Now execute the script and see the magic :)))

</details>

## Functions
