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
name = parsa
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
#!/bin/bash

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

We can also do mathematical operations as well:

```bash
#!/bin/bash

# gouss law
for i in {0..10}
do
  sum=$((sum+i))
done

echo "sum of first 10 integers are: $sum"
echo "sum of first 10 integers are: $(((10+0)*11/2))"
```

We can use the output of a command in another command. For instance:

```shell
$ ./hello.sh $(whoami) mahyar
parsa says hello to mahyar
```
