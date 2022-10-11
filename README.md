# Linux Notes
A rather complete Linux cheat sheet
# Introduction
Linux is an open-source Unix-like operating system based on the Linux kernel, an operating system kernel first released on September 17, 1991, by Linus Torvalds. Linux is typically packaged as a Linux distribution.
## Linux Distributions ("Distro"s)
Linux is one of the most popular operating systems, with around 3-3.5 billion users worldwide. Thanks to its extensibility and nature as an open-source, it has led to the creation of many Linux-based distributions that have strong features.
### The most popular linux distributions:
![](https://preview.redd.it/80so7f9nna751.png?width=960&crop=smart&auto=webp&s=0d394083088dd9cc1e36868b99527779d0241d02) <br>
You can find a complete tree of linux distros [here](https://upload.wikimedia.org/wikipedia/commons/b/b5/Linux_Distribution_Timeline_21_10_2021.svg)
## What are "shell" and "terminal" ?
### **Shell**
Shell is an interface that connects you to the operating system (OS) and lets you work with it. Shell is responsible for interpreting commands and return the results back. The default shell in ubuntu (and many other distros) is _**bash**_.
### **Terminal**
Terminal is a graphical software that you can access any shell you want through it.
![image](https://user-images.githubusercontent.com/92635013/195100325-217ca755-2767-470c-995d-fbf9fa89c065.png)
## General Structure of Linux Commands
```
COMMAND [OPTIONS] [ARGUMENTS]
```
- **COMMAND:** This part is the command that is sent to the OS. Every command is a program that tells the OS to do something.
- **OPTIONS:** We can put zero or more options here. They specify the details of our command. Options are denoted by **_"-"_** or **_"--"_** sign.
- **ARGUMENTS:** These are the inputs that the command is going to operate on.

**be aware:** All of above parts are case sensitive.
# 1) Basic Commands
## echo
```
echo <argument>
```
The simplest command in linux is `echo` which simply prints out every argument that is passed to it. Try typing `echo hello linux!` in your terminal!
## pwd
```
pwd
```
In linux, a **directory** is something that contains some other files and directories. When you open the _terminal_, you are in `/home/<username>` by default (where `<username>` is your account name). <br>
By entering `pwd` in your terminal (which stands for `print work directory`), you can see where you are in the file system.
## cd
```
cd <address>
```
`cd` stands for `change directory` and as its name implies, we can use it to move in the file system.
(`<address>` can be either relative or absolute) <br><br>
**~** : This sign stands for the current user's home directory which is `/home/<username>`. For example `cd ~/Downloads/` will move me to `/home/parsa/Downloads/`.
## ls
```
ls [OPTIONS]... [FILE]...
```
This command, lists information about the FILEs (We often use this command without any arguments which takes the current directory as argument by default)
### important options:
|option  |effect  |
|:-------|:-------|
|-a or --all|do not ignore entries starting with .|
|-l|use a long listing format (in more details)|
|-h or --human-readable|with -l and -s, print sizes like 1K 234M 2G etc.|
|-r or --reverse|reverse order while sorting|
|-t|sort by time, newest first|
## history
```
history [<number of commands>]
```
If we enter `history` in terminal, we can see the complete history of our entered commands. We can also restrict the number of commands to see. For instance, by entering `history 3`, we can see our last 3 commands. <br>
Moreover, we are able to clear our history using `history -c` command.
## mkdir
