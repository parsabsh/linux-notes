# Table of Contents

- [Table of Contents](#table-of-contents)
- [Introduction](#introduction)
  - [Linux Distributions ("Distro"s)](#linux-distributions-distros)
    - [The most popular linux distributions](#the-most-popular-linux-distributions)
  - [What are "shell" and "terminal" ?](#what-are-shell-and-terminal-)
    - [Shell](#shell)
    - [Terminal](#terminal)
  - [General Structure of Linux Commands](#general-structure-of-linux-commands)
  - [Some Useful Ubuntu Shortcuts](#some-useful-ubuntu-shortcuts)
- [1) Basic Commands](#1-basic-commands)
  - [echo](#echo)
  - [pwd](#pwd)
  - [cd](#cd)
  - [ls](#ls)
  - [history](#history)
  - [mkdir](#mkdir)
  - [rmdir](#rmdir)
  - [touch](#touch)
  - [cat](#cat)
  - [cp](#cp)
  - [mv](#mv)
  - [rm](#rm)
  - [date](#date)
  - [Standard Streams](#standard-streams)
  - [Redirection](#redirection)
  - [Pipelines](#pipelines)
  - [Package Managers](#package-managers)
- [2) Files and Strings](#2-files-and-strings)
  - [du and file commands](#du-and-file-commands)
  - [Vim editor](#vim-editor)
    - [Introduction and Installation](#introduction-and-installation)
    - [Vim Modes](#vim-modes)
      - [1) Command Mode](#1-command-mode)
      - [2) Insert Mode](#2-insert-mode)
    - [How to learn vim?](#how-to-learn-vim)
  - [Linux File System](#linux-file-system)
  - [View File Contents](#view-file-contents)
    - [more](#more)
    - [less](#less)
    - [head](#head)
    - [tail](#tail)
    - [cut](#cut)
    - [wc](#wc)
    - [sort](#sort)
    - [grep](#grep)
    - [find](#find)
    - [wildcards](#wildcards)
    - [brace expansion](#brace-expansion)
  - [File Compression](#file-compression)
    - [gzip](#gzip)
    - [bzip2](#bzip2)
    - [Archive Multiple Files](#archive-multiple-files)
  - [awk](#awk)
- [3) Permissions](#3-permissions)
  - [Linux Accounts and Groups](#linux-accounts-and-groups)
    - [User](#user)
    - [Group](#group)
    - [/etc/passwd](#etcpasswd)
  - [Manage Users and Groups](#manage-users-and-groups)
    - [Create and Delete Users](#create-and-delete-users)
    - [Create and Delete Groups](#create-and-delete-groups)
    - [Change User Properties](#change-user-properties)
  - [The root User](#the-root-user)
  - [File and Directory Permissions](#file-and-directory-permissions)
    - [View File Permissions](#view-file-permissions)
    - [Change File Owner](#change-file-owner)
    - [Change Permissions](#change-permissions)
- [4) Scripting](#4-scripting)
  - [Variables](#variables)
  - [Arrays](#arrays)
    - [Append](#append)
    - [Access Elements](#access-elements)
  - [Hashmaps](#hashmaps)
  - [Conditional Statements](#conditional-statements)
    - [if-then](#if-then)
    - [if-then-else](#if-then-else)
    - [if-elif-else](#if-elif-else)
    - [switch-case](#switch-case)
    - [test command](#test-command)
  - [Loops](#loops)
    - [For Loops](#for-loops)
    - [While Loops](#while-loops)
  - [Options and Arguments](#options-and-arguments)
  - [Other Topics](#other-topics)
    - [Functions](#functions)
    - [Mathematical Operations](#mathematical-operations)
    - [Command Substitution](#command-substitution)
- [5) Processes](#5-processes)
  - [What is a "Kernel"?](#what-is-a-kernel)
  - [uname command](#uname-command)
  - [What is a "process"?](#what-is-a-process)
  - [Process Management Commands](#process-management-commands)
    - [jobs](#jobs)
    - [bg](#bg)
    - [fg](#fg)
    - [top and htop](#top-and-htop)
    - [nice and renice](#nice-and-renice)
    - [ps](#ps)
  - [Process Lifecycle](#process-lifecycle)
  - [/proc directory](#proc-directory)
  - [Signals and kill Command](#signals-and-kill-command)
  - [Sessions and Groups](#sessions-and-groups)

**NOTE:** Pictures and diagrams without mentioned source are taken from Quera.ir.

# Introduction

Linux is an open-source Unix-like operating system based on the Linux kernel, an operating system kernel first released on September 17, 1991, by Linus Torvalds. Linux is typically packaged as a Linux distribution.

## Linux Distributions ("Distro"s)

Linux is one of the most popular operating systems, with around 3-3.5 billion users worldwide. Thanks to its extensibility and nature as an open-source, it has led to the creation of many Linux-based distributions that have strong features.

### The most popular linux distributions

![reddit](https://preview.redd.it/80so7f9nna751.png?width=960&crop=smart&auto=webp&s=0d394083088dd9cc1e36868b99527779d0241d02)

You can find a complete tree of linux distros [here](https://upload.wikimedia.org/wikipedia/commons/b/b5/Linux_Distribution_Timeline_21_10_2021.svg)

## What are "shell" and "terminal" ?

### Shell

Shell is an interface that connects you to the operating system (OS) and lets you work with it. Shell is responsible for interpreting commands and return the results back. The default shell in ubuntu (and many other distros) is _**bash**_.

### Terminal

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

_**NOTE**_: Super key is the key with windows sign on it (= Windows key).
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

**NOTE:** We can use `.` and  `..` in the `<address>` part. `.` is `current directory` and `..` is `parent directory`. For example if we are in `/home/parsa` and we run `cd ..`, we will be moved to `/home`.

**~** : This sign stands for the current user's home directory which is `/home/<username>`. For example `cd ~/Downloads/` will move me to `/home/parsa/Downloads/`.

## ls

```bash
ls [OPTIONS]... [FILE]...
```

This command, lists information about the FILEs (We often use this command without any arguments which takes the current directory as argument by default)

**_important options_**

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

```bash
mkdir [OPTION]... DIRECTORY...
```

This command creates the `DIRECTORY(ies)`, if they don't already exist.

**An important option:** If we want to make nested directories with normal `mkdir` commands, we should do this:

```bash
mkdir parent
cd parent/
mkdir child
```

But using `-p` or `--parents` option, we can do it in a single command:

```bash
mkdir -p parent/child
```

## rmdir

```bash
rmdir [OPTIONS]... [DIRECTORY]...
```

This command removes `DIRECTORY(ies)` if they're empty. We have the `-p` option just like the one we had in `mkdir` command.

To remove a non-empty directory, we should use `rm` command which we will learn about later.

## touch

```bash
touch file_name
```

This command creates a new file, if it doesn't already exist. Otherwise, it will update the modification time of the existing file to the current time.

## cat

```bash
cat [OPTION]... file_name
```

We can see contents of a file using `cat` command. This command has some useful options like `-n` for printing line numbers, `-b` for ignoring blank lines, and so on. Use `cat --help` for more information.

<details>
<summary><b>Use of cat in redirections</b></summary>

If `cat` command is used without any arguments, it will copy stdin into stdout. This attribute is useful in redirection (which we will learn about in a minute).

For example we can use the following command to simply write in a file:

```bash
cat > file_name
```

Try it :)

</details>

## cp

```bash
cp SOURCE DEST
```

We use `cp` simply to copy a file or directory. For directories, we should use `-r` option to copy recursively.

## mv

```bash
mv SOURCE DEST
```

This command moves a file or directory (You can think about it like _cut_ and _paste_). As always, don't forget to use `--help` or `man` for more information :)

**NOTE:** We also use `mv` command to **rename** files.

## rm

```bash
rm [OPTION]... FILE...
```

We use `rm` to delete a file or directory. Note that to delete a non-empty directory, we use `rm -r` to remove recursively.

## date

```bash
date [OPTION]... [+FORMAT]
```

This command is a powerful tool to see the time in any desired format.

To output the current time in a specific format, we use `date '+FORMAT'` where `FORMAT` can be made using the following characters (This is from `date --help`):

```
FORMAT controls the output.  Interpreted sequences are:

  %%   a literal %
  %a   locale's abbreviated weekday name (e.g., Sun)
  %A   locale's full weekday name (e.g., Sunday)
  %b   locale's abbreviated month name (e.g., Jan)
  %B   locale's full month name (e.g., January)
  %c   locale's date and time (e.g., Thu Mar  3 23:05:25 2005)
  %C   century; like %Y, except omit last two digits (e.g., 20)
  %d   day of month (e.g., 01)
  %D   date; same as %m/%d/%y
  %e   day of month, space padded; same as %_d
  %F   full date; like %+4Y-%m-%d
  %g   last two digits of year of ISO week number (see %G)
  %G   year of ISO week number (see %V); normally useful only with %V
  %h   same as %b
  %H   hour (00..23)
  %I   hour (01..12)
  %j   day of year (001..366)
  %k   hour, space padded ( 0..23); same as %_H
  %l   hour, space padded ( 1..12); same as %_I
  %m   month (01..12)
  %M   minute (00..59)
  %n   a newline
  %N   nanoseconds (000000000..999999999)
  %p   locale's equivalent of either AM or PM; blank if not known
  %P   like %p, but lower case
  %q   quarter of year (1..4)
  %r   locale's 12-hour clock time (e.g., 11:11:04 PM)
  %R   24-hour hour and minute; same as %H:%M
  %s   seconds since 1970-01-01 00:00:00 UTC
  %S   second (00..60)
  %t   a tab
  %T   time; same as %H:%M:%S
  %u   day of week (1..7); 1 is Monday
  %U   week number of year, with Sunday as first day of week (00..53)
  %V   ISO week number, with Monday as first day of week (01..53)
  %w   day of week (0..6); 0 is Sunday
  %W   week number of year, with Monday as first day of week (00..53)
  %x   locale's date representation (e.g., 12/31/99)
  %X   locale's time representation (e.g., 23:13:48)
  %y   last two digits of year (00..99)
  %Y   year
  %z   +hhmm numeric time zone (e.g., -0400)
  %:z  +hh:mm numeric time zone (e.g., -04:00)
  %::z  +hh:mm:ss numeric time zone (e.g., -04:00:00)
  %:::z  numeric time zone with : to necessary precision (e.g., -04, +05:30)
  %Z   alphabetic time zone abbreviation (e.g., EDT)
```

To see a specific time we can use `--date` option. See the following example:

```shell
$ date --date="2 year ago"
Fri Oct 16 12:13:24 AM +0330 2020
$ date --date="34 sec ago"
Sun Oct 16 12:13:50 AM +0330 2022
```

## Standard Streams

A **stream** is simply a river of data. Linux commands (or more precisely, linux _processes_) talk to each other in terms of streams.

Each linux process has three **standard streams** to communicate with others. It gets and gives data through them. The standard streams are **"Standard Input"**, **"Standard Output"**, and **"Standard Error"**. Each of them has a code which you can see here:

![stream](https://user-images.githubusercontent.com/92635013/196439211-22a117f1-61a5-4a2f-805b-8560f5c0f4b9.png)


- **stdin:** The command can get its input through stdin (standard input) stream. In raw use of commands, the stdin comes from keyboard as you type in the terminal.

- **stdout:** While the command is running, it sends some outputs that go through the stdin (standard output). In raw use of commands, the stdout stream is shown in the terminal.

- **stderr:** During the execution of a process, it may encounter an error. The program sends errors through the stderr (standard error) steam. In raw use of commands, the stderr stream is shown in the terminal too.

## Redirection

Redirection is a way to use files as stdin and stdout instead of terminal. Namely, we can either give a file to a command as its standard input or save the standard output of a command in a file.


Here are different types of redirections:

```shell
$ echo "Put this in file.txt" > file.txt  # overwrite the file
$ echo "Add this to file.txt" >> file.txt  # append to the file
$ wc < file.txt  # give the file as input of wc command
$ cat << MARKER > file.txt  # another way of giving input to a command's stdin 
some
data
here
MARKER
```

## Pipelines

Pipelines let us give the output of a command as input of another one. Consider the following picture:

![pipe](https://user-images.githubusercontent.com/92635013/196032588-5bb357fc-5297-4195-b0fa-3b81696c8cee.png)

Using pipelines, we can combine multiple commands and make powerful commands to do a lots of things in a single line.

The general structure of piplines is like this:

```bash
command1 | command2 | ...
```

As an example, here I introduce a pipline which I often use when I want to find out a specific option of a command:

```bash
COMMAND --help | grep "what I'm looking for"
```

Use it and enjoy :)

## Package Managers

Package Managers are essentially software applications that help users to: Search, Download, Install, Remove and Update software applications on their computer. Experienced Linux users will very rarely download software from websites or any other location. The primary reasons for this included aspects as ease of use, security and the fact that most Linux distributions have a list of sources where users can download free open source software packages.

For most novice users of Linux, the most common and popular package managers they are likely to first start using is the `apt` (Advanced Package Tool) because it is most widely shipped as the default Package Manager for users of Debian, Ubuntu and Mint. We will cover some basic and common commands of `apt`:

First of all, we update our package manager, meaning that it updates its package list if there is any new package or new version of a package is available.

```bash
sudo apt update
```

We can also search for a package:

```bash
sudo apt search [PACKAGE_NAME]
```

Then we can install a package:

```bash
sudo apt install [PACAKGE_NAME]
```

If we don't want a package anymore, we can delete it:

```bash
sudo apt remove [PACKAGE_NAME]
```

By executing the following command, if there is a new version available for a package that has been already installed, it will upgrade to the new version:

```bash
sudo apt upgrade
```

# 2) Files and Strings

## du and file commands

```bash
du [OPTIONS] [ARGUMENT]
```

This command indicates the _disk usage_ (as its name implies) and can be used without arguments in which the current directory is passed by default. Some of its useful options are `-h, --human-readable`, `-s, --summarize`, `-c, --total`, and `--time`.

```bash
file [OPTIONS] file_name
```

This command determines type of a file. In Linux, _file extensions_ don't matter, So `file` command helps us to figure out the file type. We can use `-b` option to get rid of extra information about the file and only see its type.

## Vim editor

### Introduction and Installation

Vim editor is among the best editors used in the command-line interface to open, edit and save files. Vim is the updated version of Vi editor that’s why vim is abbreviated as “Vi improved”.

To install vim, enter `sudo apt install vim -y` in your terminal. Then to open a file in vim, use the following command (It will create a file if it doesn't exist):

```bash
vim file_name
```

### Vim Modes

Now you are in the vim environment. Vim has two modes:

#### 1) Command Mode

When you open any file with vim, you are in the command mode by default. In command mode, you can perform different tasks by using the commands for example to delete a line, to copy the line, and to navigate the cursor in any specified position of the file. If for any reason you are not in the command mode, simply press the `ESC` key, to enter in the command mode.

**Crucial Note:** To save changes, just enter `:w` in command mode and to exit vim, enter `:q`.

#### 2) Insert Mode

To insert something, you have to choose the insert mode, for this purpose, simply press the `i` key to enter the insert mode. In this mode, you can write anything and can add anything to the file.  Once you are done by inserting, press `ESC` key from keyboard and switch insert mode to command-line mode.

### How to learn vim?

There are an infinite number of commands in vim :) but you don't need to learn them all when you start working with it. As you go further in vim, you'll find new commands one by one based on your needs. So the best way of learning vim is to just **use it** every day.

But if you are qiute new to vim, start with vimtutor. Simply type `vimtutor` command in your terminal. This is a good way to start working with vim.

## Linux File System

In Linux and many other operating systems, directories can be structured in a tree-like hierarchy. All the files are arranged as a tree and its branches. The topmost directory called the **root (/) directory**. All other directories in Linux can be accessed from the root directory.

The following figure summarizes Linux standard file system hierarchy:

![linux](https://user-images.githubusercontent.com/92635013/205032787-6e77f2c6-968b-4be2-adc9-5fe5a0afba7a.jpg)

Be sure to refer to the official Linux [Filesystem Hierarchy Standard (FHS)](https://www.pathname.com/fhs/) web page for details about each of these directories and their many subdirectories. Wikipedia also has a good description of the [FHS](https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard). This standard should be followed as closely as possible to ensure operational and functional consistency.

## View File Contents

We have already learned the `cat` command to view files. Here, we introduce some more commads to do this.

**NOTE:** All of the following commands also work for multiple files.

### more

This command is for better viewing long text files in terminal. Using this command, we can view the file one page at a time. We can also move in the file with arrow keys. Some keys we can use in `more` command:

- `space`: Next page
- `enter`: Next line
- `B`: Previous page
- `=`: Current line number
- `q`: Exit back to terminal

If we want to display file beginning from line number `N`, we should open the file like this:

```bash
more +<N> example.txt
```

### less

This command is like `more`, but it has more advanced options! Some of them are given here:

- `G`: First page
- `Shift + G`: Last page
- `:<N>`: Go ahead `N` lines
- `/[string]`: Search forward for the specified string
- `?[string]`: Search backward for the specified string
- `N`: Next match during a search
- `Shift + N`: Previous match during a search

These two commands are faster with big files because they load them page by page (a text editor loads the whole file into the memory), so these commands are often used in pipelines too. If you want to see the results of a command which takes a lot of time to completely execute, just pass the output to `less` or `more`. For instance, if you want to see all log files of your system, you can run:

```bash
find / -name "*.log" | less
```

### head

Prints the first 10 lines of a file. To change this number, there are two options:

- `-c, --bytes=[-]NUM`: Print the first NUM bytes; with the leading '-', print all but the last NUM bytes
- `-n, --lines=[-]NUM`: Print the first NUM lines; with the leading '-', print all but the last NUM lines

### tail

Prints the last 10 lines of a file. To change this number, there are two options:

- `-c, --bytes=[+]NUM`: Print the last NUM bytes; or use -c +NUM to print starting with byte NUM
- `-n, --lines=[+]NUM`: output the last NUM lines; or use -n +NUM to output starting with line NUM

As always, we can use these command in pipeline. For example, suppose we want to print lines 117 to 122 of a file. We can use the following pipeline command:

```bash
cat file.txt | head -n 122 | tail +117
```

### cut

This command is used to print selected parts of lines of a file. Suppose we want to print the first 5 characters of each line of the file. We can use `-b` or `-c` options:

```bash
cut -b 1-5 file.txt
```

If we do not type any number on each side of `-`, it will be interpreted as the end or beginning of the line. For instance, the following command prints from the 8th character to the end of each line:

```bash
cut -c 8- file.txt
```

Suppose we have a `.csv` file in which fields are delimited using the character `","` and we want to print only some columns of it (let's say 2nd and 4th columns). We first specify the delimiter using `-d` option and then we select the field we want using `-d` option:

```bash
cut -d "," -f 2,4 file.csv
```

Note that the default output delimiter is the input delimiter. If we want to specify our own desired output delimiter, we could use `--output-delimiter=STRING`.

### wc

This command prints line, word, and byte count for a file. Some of its option are listed below:

- `-c, --bytes`: print the byte counts
- `-m, --chars`: print the character counts
- `-w, --words`: print the word counts
- `-l, --lines`: print the newline counts
- `-L, --max-line-length`: print the maximum display width

### sort

Using this command, we will be able to sort the output (i.e. the content of files). Some important options are given here:

- `-f, --ignore-case`: fold lower case to upper case characters
- `-r, --reverse`: reverse the result of comparisons
- `-n, --numeric-sort`: compare according to string numerical value
- `-k, --key=[KEYDEF]`: sort via a key; KEYDEF gives location and type
- `-t, --field-separator=SEP`: use SEP instead of non-blank to blank transition

Suppose we have a `.csv` file and we want to sort according to the values in the third column. We can do this by `sort` command in the following manner:

```bash
sort -t ',' -k 3 -n -r << EOF
parsa,bashari,19,pass
amir,hamidzade,17,pass
alireza,sohrabi,20,pass
ehsan,karbalae,8,fail
arash,ziyae,18,pass
reza,dadashpoor,4,fail
EOF
```

and the output will be:

```bash
alireza,sohrabi,20,pass
parsa,bashari,19,pass
arash,ziyae,18,pass
amir,hamidzade,17,pass
ehsan,karbalae,8,fail
reza,dadashpoor,4,fail
```

### grep

This command is a powerful tool for searching for a pattern in files. The total structure of this command is as follows:

```bash
grep [OPTION]... PATTERNS [FILE]...
```

Note that patterns are in **regex** format. If you are not familiar with regex or regular expressions, you can see [this tutorial](https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285). For practicing and testing your regular expressions, [regex101](https://regex101.com/) is a very useful tool.

grep has a lot of useful options which enable you to perform complicated searches. So, it is highly recommended to run `grep --help` and see them all. But here is a list of some useful options of this command:

- `-i, --ignore-case`: ignore case distinctions in pattern and data
- `-w, --word-regexp`: match only whole words
- `-v, --inverse-match`: select non-matching lines
- `-c, --count`: print only a count of selected lines
- `-n, --line-number`: print line number with output lines
- `--color`: use markers to highlight the matching string

For example, suppose we want to see errors and warnings when compiling a C program. We can use the following command:

```bash
gcc test.c |& grep --color -iE "error|warning"
```

Note that the `|&` is a way to send `stderr` instead of `stdout` through the pipeline to the next command. As a practice, search about `-E` option (obvoiusly first see `--help`).

### find

This command is used to searching files in terminal. It doesn't obey general structure of previous commands and it has the following structure:

```bash
find <where to start searching> <expression determines what to find> <-options> <what to find> 
```

**-name option**: With this option we specify the name of files or directories we are looking for. For instance:

```bash
find . -name "file/dir name"
```

**-type option**: If we are only looking for files with that name, we use this option with `f` (for directories we use `d`). For example:

```bash
find . -type d -name "dir name"
```

**-size [+/-] [SIZE] [c/k/M/G]**: We can specify our desirable size using this option. Consider the following examples:

```bash
find . -type f -size 100c  # exactly 100 bytes
find . -type f -size +1M   # more than 1 megabyte
find . -type f -size +100k -size -800k  # between 100 and 800 kilobytes
```

**-maxdepth and -mindepth options**: We can specify the maximum and minimum depth of search in the directories with these options.

**-empty**: This option only shows empty files and directories. For example, if we are looking for empty directories in at maximum depth of 2, we can use the following command:

```bash
find . -type d -maxdepth 2 -empty -name "dir name"
```

`find` has two parts **search** and **action**. We told about the search part. Now, we introduce the action part.

We can do an operation on each of our search results. The default action in the `find` command is `-print`. We can change this by the `-exec` option. Using this action, we can perform commands on the results of `find` command. For example we want to show the type of each file:

```bash
find . -name *.py -exec file {} \;
```

The arguments of `-exec` are:

- **Command**: Every command that is executabe in our shell
- **Placeholder**: The `{}` is the place where the search results will be in
- **Delimiter**: A sign to show that the command is finished. We can use `+` or `;`. The `;` sign run `n` commands where `+` runs one command with `n` arguments.

We can use `-delete` action to delete the found files.

### wildcards

Wildcard characters in Unix/Linux allow the matching of files in an abstracted way. Three main wildcards are:

1. **\***: Zero or more characters
2. **?**: One character
3. **[ ]**: One of the characters between brackets

For instance, if we have downloaded a large video file that was split into lots of small chunks. What is the easiest way to merge them back into one single video? If the files were named as `ironman.001.mpeg` to `ironman.099.mpeg`, we could merge them through one line of command:

```bash
cat ironman.*.mpeg > ironman.mpeg
```

or we can do this:

```bash
cat ironman.0??.mpeg > ironman.mpeg
```

### brace expansion

For example, suppose we want to download a whole season of a TV series. We could do this using brace expansion:

```bash
wget download.example.com/Friends.S04.E{01..24}.mkv
```

Note that brace expansion also works for english letters (e.g. `{p..w}`).

## File Compression

Compression of big files is an important task in the data age. Here we introduce some basic compression capabilites of linux. To start, we need a large file to perform compression. We create a file with size of 100M using the following command:

```bash
cat /dev/random | tr -dc "[:alpha:]" | head -c 100M > largefile
```

### gzip

This command enables us to compress a large file to a `.gz` file:

```bash
gzip largefile
```

You can check the result with `ls -lh`. Then we can decompress `largefile.gz` file using `gunzip` command:

```bash
gunzip largefile.gz
```

### bzip2

This command is similar to `gzip` but make more compression and also take longer to compress. The compress and decompress commands are really similar to gzip:

```bash
bzip2 largefile
bunzip2 largefile.bz2
```

### Archive Multiple Files

In `gzip` and `bzip2` commands, we could only compress one giant file. In order to compress multiple files into a single file, we first need to put them together in a largefile and then compress it using previous commands. The process of putting together in linux is called **archiving**. We use `tar` command to do so. It has so many options and as usual I recommend to see `tar --help` for more information.

To create a new archive, use `-c` option and to specify the files, use `-f` option.

```bash
tar -cf archive.tar foo bar  # Create archive.tar from files foo and bar
tar -cvf archive.tar file{3..10} folder{1..2}  # -v option prints the file names
```

Using `-t` option, you can see the list the contents of an archive.

```bash
tar -tf archive.tar
```

Then we can use `-x` to extract files from an archive.

```bash
tar -xf archive.tar
```

Although we can manually compress the generated tar file using `gzip`, the `tar` command has provided us with a option (`-z, --gzip`) to do this automatically.

```bash
tar -zcvf friends.tar.gz friends.S03.E{01..24}
```

Then we can decompress and extract our files using the following command:

```bash
tar -zxvf friends.tar.gz
```

We can use `-j, --bzip2` instead of `-z` to do the compression using `bzip2`.

## awk

Awk is a scripting language used for manipulating structured data and generating reports. The general structure of this command is:

```bash
awk '{action}' file
```

We can apply different actions but we here only cover `print`. Suppose we have a `.csv` file. We can print the second and fourth columns using the following command:

```bash
awk '{print $2, $4}' data.csv
```

We can use `$NF` variable to access last column.

```bash
awk '{print $1, $NF}' data.csv
```

We also can use regex to select only rows that match a specific pattern. In this case, the general structure of `awk` command becomes this:

```bash
awk '/REGEX/{action}' file
```

`awk` command is a very broad topic and I'm not explain it in details here. But I highly recommend to search and learn it. You can start by reading this [geeksforgeeks tutorial](https://www.geeksforgeeks.org/awk-command-unixlinux-examples/).

# 3) Permissions

Linux’s major difference from other operating systems is its ability to have multiple users. Linux is designed to allow more than one user to have access to the system at the same time. In order for this multiuser design to work properly, there needs to be a method to protect users from each other. This is where permissions come in to play.

**NOTE:** For more information on the topics in this chapter, I recommend to see [here](https://www.linode.com/docs/guides/linux-users-and-groups/).

## Linux Accounts and Groups

### User

A user is an entity that can manipulate files and perform several other operations. Each user is assigned an ID that is unique for each user in the operating system.

Linux-based systems have two types of users: system and normal users. System users are entities created by the system to run non-interactive processes, i.e., the processes that run in the background and do not require human interaction.

After installation of the operating system, the ID 0 is assigned to the root user and the IDs 1 to 999 (both inclusive) are assigned to the system users and hence the ids for local user begins from 1000 onwards.

### Group

Groups are collections of users. Creating and managing groups is one of the simplest ways to deal with multiple users simultaneously, especially when dealing with permissions. So, instead of manipulating each user's permissions one by one, we just need to add it to a group with some specific set of permissions.

### /etc/passwd

A record of the users of a system is stored in the file `/etc/passwd`. Each line of this file represents a user account in the following format:

```bash
[username]:[password]:[UID]:[GID]:[Extra Info]:[home directory]:[shell]
```

The `GID` here is the _Primary Group_ ID. When a Linux user logs into their system, the primary group is usually the default group associated with the logged in account.

To find my account information in this file, I use the `whoami` command which returns the username of the logged in user:

```bash
cat /etc/passwd | grep $(whoami)
```

and the output will be something like this:

```bash
parsa:x:1000:1000:parsa,,,:/home/parsa:/bin/bash
```

You can see that there is an `x` in the password field. This is due to the fact that your OS stores the encoded value of passwords in `/etc/shadow` which as a normal user, you do not have permission to read.

Using `id` command, you can see user and group information about each specified user or (when user omitted) for the current user.

**Curiosity**: This file is a good file to practice what you learned in the previous chapter on. Try `awk` and `sort` commands on it.

## Manage Users and Groups

**NOTE**: You may need root privilages to execute some of the following commands. We will discuss about root user later. For now, just add `sudo` before your commands.

### Create and Delete Users

To create a new standard user, use the `useradd` command. The syntax is as follows:

```bash
useradd [options] username
```

Some useful options are shown here:

- `-d, --home-dir [HOME_DIR]`: home directory of the new account
- `-e, --expiredate [EXPIRE_DATE]`: expiration date of the new account
- `-m, --create-home`: create the user's home directory
- `-s, --shell [SHELL]`: login shell of the new account

You need to set a password for the new user by using the `passwd` command. The syntax is as follows:

```bash
passwd username
```

There is another way to create a new user which is easier. Instead of `useradd`, try `adduser`! It will ask you some questions (most of them are optional).

After you created a new user, go and check `/etc/passwd` last row. You will see there is a new account added to this file, and also a new group has been created as its primary group.

In order to delete a user account, we can use `deluser` or `userdel` commands. There both have options for deleting the home directory and the files owned by the user. User their help pages to find out.

### Create and Delete Groups

There are two commands for creating a new group, just like the ones for creating a new user:

```bash
sudo groupadd name
sudo addgroup name
```

In order to delete a group, we can use `delgroup` or `groupdel` commands. As always, see the help pages!

### Change User Properties

The `usermod` command is used to change user properties. Some of its options are here:

- `-g, --gid [GROUP]`: force use GROUP as new primary group
- `-G, --groups [GROUPS]`: new list of supplementary GROUPS
- `-a, --append`: append the user to the supplemental GROUPS mentioned by the -G option without removing the user from other groups
- `-d, --home HOME_DIR`: new home directory for the user account
- `-m, --move-home`: move contents of the home directory to the new location (use only with `-d`)
- `-u, --uid`: new UID for the user account
- `-s, --shell`: new login shell for the user account

So, in order to add a user to a group, we should run the following command:

```bash
sudo usermod -aG [groupname] [username]
```

Now, if you run `id [username]`, you will see that the new group is added to its groups list.

To delete a user from a group, we can use `gpasswd` command with `-d` option, or we can simply do it using `deluser` command with two arguments as follows:

```bash
sudo deluser [username] [groupname]
```

## The root User

`root` is the super user and has the ability to do anything on a system. If you have the password of root user, you can login to the root account using `su` command and then logout using `exit` command. In order to have an additional layer of security, a `sudo` user is generally used in place of root. While `sudo` is used to give another user limited access to another user’s account for the purpose of performing tasks (in most cases the root user or the superuser), `sudo` may be best explained as a tool that allows users and groups to have access to commands they normally would not be able to use. `sudo` enables a user to have administration privileges without logging in directly as `root`. A sample of the `sudo` command is as follows:

```bash
sudo apt-get install [package]
```

In order to provide a user with the `sudo` ability, they need to be added to a `sudo` enabled group, or their username needs to be added to the `sudoers` file with a set of permissions. This file is sensitive and important as an access and security control, and should not be edited directly with a text editor. If the sudoers file is edited incorrectly it could result in preventing access to the system or other unintended permission changes.

The `visudo` command should be used to edit the `sudoers` file. At a command line, log into your system as `root` and enter the command `visudo`. For more information see [here](https://www.linode.com/docs/guides/linux-users-and-groups/#whitelisting-commands-with-sudo).

## File and Directory Permissions

Permissions are the “rights” to act on a file or directory. The basic rights are read, write, and execute.

- **Read**: a readable permission allows the contents of the file to be viewed. A read permission on a directory allows you to list the contents of a directory.
- **Write**: a write permission on a file allows you to modify the contents of that file. For a directory, the write permission allows you to edit the contents of a directory (e.g. add/delete files).
- **Execute**: for a file, the executable permission allows you to run the file and execute a program or script. For a directory, the execute permission allows you to change to a different directory and make it your current working directory.

### View File Permissions

To view the permissions on a file or directory, issue the command `ls -l` or `ll`:

```txt
-rw-r--r-- 1 root root 2887 Jul 28 13:31 /etc/passwd
```

The first ten characters show the access permissions. The first dash (`-`) indicates the type of file (`d` for directory, `s` for special file, and `-` for a regular file). The next three characters (`rw-`) define the owner’s permission to the file. In this example, the file owner has read and write permissions only. The next three characters (`r--`) are the permissions for the members of the same group as the file owner (which in this example is read only). The last three characters (`r--`) show the permissions for all other users and in this example it is read only. The following picture gives a summary:

**Picture here**

### Change File Owner

As we mentioned before, each file or directory has two owners: a _user owner_ and a _group owner_. The `chown` command enables us to change these owners. The general structure of this command is:

```bash
sudo chown [USER]:[GROUP] [FILE]  # l
```

### Change Permissions

One of the most useful commands which enables us to change the permissions of a file or a directory, is `chmod` (i.e. change mode). This command can be used in two different ways:

```bash
chmod MODE[,MODE,...] FILE  # using letters
# where each MODE is of the following format:
[ugoa][+-=][rwx]
```

or

```bash
chmod OCTAL-MODE FILE  # using numbers
```

In the first method, each character has its own meaning:

- `u`: file owner
- `g`: group owner
- `o`: all other users
- `a`: all users, identical to `ugo`
- `+`: grant permission
- `-`: remove permission
- `=`: replace (set) permissions
- `r`: read permission
- `w`: write permission
- `x`: execute permission

For instance, consider the following command:

```bash
chmod u+rw,go-w,a-x file.sh
```

This command grants read and write permissions to the file owner. Then it gets the write permission from group owner and all other users. Finally, it removes execute permission from all users. If we run `ls -l` before and after this command, we maight see something like this:

```bash
$ ls -l
-r-xrw-r-- 1 parsa parsa   25 Jul 28 16:15 file.sh
$ chmod u+rw,go-w,a-x file.sh
$ ls -l
-rw-r--r-- 1 parsa parsa   25 Jul 28 16:15 file.sh
```

In the second method, we put 0 or 1 instead of each letter in `rwx` and the read the result number in binary format. Then we do this for three groups (file owner, group owner, and other users) and we put the three numbers together to form a 3-digit number. For instance, we show `r-xrw---x` by `561` in the following command:

```bash
$ chmod 561 file.sh
$ ls -l
-r-xrw---x 1 parsa parsa   25 Jul 28 16:15 file.sh
```

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

**NOTE:** There is a subtle difference between if statements in bash and other languages. In other languages, the conditional term is either True of False. But in bash, it's a command. If the command is executed successfully (with exit code `0`), then the `commands` will be executed (and otherwise, they won't).

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

   **NOTE:** The `"` character is optional unless the elements have special characters like `'`, `space`, etc.
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

**NOTE:** We can use `break` and `continue` statements just like every other language.

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

## Other Topics

### Functions

We can define functions in bash, but they're a little bit different from other languages in passing arguments and using them. See the following example:

```bash
#!/bin/bash
function hello_world {
  echo hello world!
}

function greet {
  echo "hello $1"  # This is how we use the arguments that have been passed to the function in bash
}

greet mirza  # This is how we pass an argument to a function in bash
greet hovakhshatara some additional arguments  # They have no effect
hello_world these are additional arguments
```

### Mathematical Operations

When we want to write a mathematical expression, we should wrap it in `$((here))`. Example:

```bash
#!/bin/bash

# gouss law
for i in {0..10}
do
  sum=$((sum+i))
done

echo sum of first 10 integers are: $sum
echo sum of first 10 integers are: $(((10+0)*11/2))
```

### Command Substitution

We can use the output of a function/command as a variable by wrapping it in ` `` `. For instance:

```bash
#!/bin/bash

# gouss law
function gauss {
  for i in {0..10}
    do
      sum=$((sum+i))
  done
  echo $sum
}

echo here is the proof that guass law was currect: `gauss` == $(((10+0)*11/2))
```

# 5) Processes

## What is a "Kernel"?

Kernel is the main part of a Operating System that has the full control over everything. It's also an interface between application software and the hardware.

![Kernel](https://upload.wikimedia.org/wikipedia/commons/thumb/8/8f/Kernel_Layout.svg/220px-Kernel_Layout.svg.png)

As always, Google it :)

The **Linux Kernel** is the thing that all Linux distros have in common. It's being managed by _**Linus Torvalds**_ in [**this repository**](https://github.com/torvalds/linux).

## uname command

```bash
uname [OPTION]...
```

This command prints certain system information. If used without options, just prints your kernel name. Options are not worth discussing here. Try `uname --help` for more information.

## What is a "process"?

Generally, a process is referred to execution of a program or command. In other words, when we execute a program or command, Linux creates (at least) one process for it. Each process uses an amount of system resources (like CPU, memory, etc.). In linux, each process is identified by a **PID(Process Identification Number)**.

A process can be executed either in _Foreground_ or _Background_. By default, shell commands are executed in _Foreground_ (and so you have to wait until the execution terminates to be able to run another foreground pocess).

## Process Management Commands

There are some commands to contorl processes:

### jobs

This command shows background processes. Each process has a _jobs ID_ that you can use in other commands like `bg`, `fg`, and `kill`.

### bg

```bash
bg %n
```

Where `n` is the _jobs ID_.

This command sends the process to background.

### fg

```bash
fg %n
```

Where `n` is the _jobs ID_.

This command sends the process to foreground.

### top and htop

`top` command is Linux's default command to see list of processes. By executing this command, you can observe executing processes and their associated system resources. This list is sorted by CPU usage by default.

For more user-friendly appearance, you can use `htop` command. This command is not installed by default on most Linux distributions and you have to use `sudo apt install htop` first. This command has an interactive environment which you can use Function Keys on your keyboard to do some changes. Try it :)

### nice and renice

If you use `top` or `htop` command, you will see a column named **NI** which stands for **Niceness**. Niceness is the priority of a process. The Linux kernel looks at the priority number to decide which process should run first.

**Niceness** is a number from -20 to 19. The higher the number, the lower the priority. To execute a command or script with a specific niceness, use `nice` command:

```bash
nice -n niceness COMMAND
```

**NOTE:** Only root user can set the nice value from -20 to 19. Other users can only set nice values from 0 to 19.

To change the niceness of a running process, use `renice` command:

```bash
renice -n niceness -p PID
```

or to change niceness of all running processes by a user:

```bash
renice -n niceness -u username
```

### ps

```bash
ps [OPTIONS]
```

This is another command for monitoring the running processes. It has a bunch of useful options that are usualy used together. For example `ps aux` is very common. As always, you can keep learning by yourself using commands' manual pages.

## Process Lifecycle

Each process in Linux has a lifecycle. The `STAT` column in `ps` command shows where the process is in its lifecycle. Consider the following image:

![Linux Process](https://totozhang.github.io/2016-01-16-linux-zombieprocess/LinuxZombie1.png)

## /proc directory

Since **_"Everything is a file"_** in Linux, processes are not exception. All processes in Linux, are tracked in a directory with address `/proc`.

If you open and work with this directory, you will learn a lot about processes. You can also use `man 5 proc` command to enter the manual page of process file system in Linux.

## Signals and kill Command

We use a signal to talk to a process. Not only us, but a signal can be sent by another process or by the OS kernel itself.

When a process recieves a signal, it decides how to react:

1) Do the signal's default operation.
2) Ignore the signal.
3) Do something else depending on the situation.

If you want to see the list of signals, type `kill -l` in your terminal. Here we introduce the most important signals:

|Signal|Shortcut|Operation|
|:-----|:-------|:--------|
|SIGINT|Ctrl + c|terminate the process|
|SIGKILL| - |kill the process (can't be ignored)|
|SIGSTOP|Ctrl + z|stop the process|
|SIGCONT| - |continue running the stopped process|

We can send signals to a process using the `kill` command in the following structure:

```bash
kill -NAME PID
or
kill -NUMBER PID
```

Where the `NAME` and `NUMBER` are the ones you saw in `kill -l` command.

## Sessions and Groups

**Group:** A set of related processes that we can send a signal to all of them at once. Each group is identified by `PGID`.

**Group Leader:** The process that has the same PID as the PGID (PID == PGID).

**Session:** Each tab in your terminal is a session. In fact, the `jobs` command displays the processes of the session in which the `jobs` command is executed. Each session is identified by `SID`.

**Session Leader:** The process that has the same PID as the SID (PID == SID). When you use `fg` command, you make a process (and the corresponding group), the session leader.

This image summarizes the definitions above:

![Groups and Sessions](https://quera.org/qbox/view/fWwTcXjVza/session.png)

**NOTE:** You can send a signal to a group or session just like a single process.
