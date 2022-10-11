# Linux Notes
A rather complete Linux cheat sheet (notes from Quera's linux course)
# Introduction
Linux is an open-source Unix-like operating system based on the Linux kernel, an operating system kernel first released on September 17, 1991, by Linus Torvalds. Linux is typically packaged as a Linux distribution.
## Linux Distributions ("Distro"s)
Linux is one of the most popular operating systems, with around 3-3.5 billion users worldwide. Thanks to its extensibility and nature as an open-source, it has led to the creation of many Linux-based distributions that have strong features.
### The most popular linux distributions:
![](https://preview.redd.it/80so7f9nna751.png?width=960&crop=smart&auto=webp&s=0d394083088dd9cc1e36868b99527779d0241d02) <br>
You can find a complete tree of linux distros [here](https://upload.wikimedia.org/wikipedia/commons/b/b5/Linux_Distribution_Timeline_21_10_2021.svg)
## What are "shell" and "terminal" ?
### **Shell**
Shell is an interface to connec and let you work with the operating system (OS). Shell is responsible for interpreting commands and return the results back. The default shell in ubuntu is _**bash**_.
### **Terminal**
Terminal is a graphical software that you can access any shell you want through it.
![image](https://user-images.githubusercontent.com/92635013/195100325-217ca755-2767-470c-995d-fbf9fa89c065.png)

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
