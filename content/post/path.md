---
title:      "PATH, FHS and $PS1"
date:       2020-02-25 08:59:00
description:    "Demystifying PATH, the Filesystem Hierarchy and PS1"
draft: false
author: Kim Schlesinger
---

This is a companion blog post for a presentation I gave at the February 2020 DenverScript Meetup.

You can find the video recording and slide deck on my [talks](/talks) page. 

## The Path Variable 
* `PATH` is an enviornment variable.
* The variable is a colon-delimited string. The directory before each colon contains executable code and is invoked through a command, like `pwd`.
* To see the value, run `echo $PATH` from your command line 
* Here's an example path: 
    
    `/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin`
    
* In the example, these are the directories in the path: 
    * `/usr/local/sbin`
    * `/usr/local/bin`
    * `/usr/sbin`
    * `/usr/bin`
    * `/sbin`
    * `/bin`

* When you type a text command and hit `RETURN` your computer looks in all the directories listed in the path, and if it finds code for the command, it will execute the program.
* Most of the built-in system commands are written in the C programming langauge.
* For MacOS and Linux, to change your path, find and edit it in your `.bash_profile`, `.bashrc` or `.zshrc` file.

### Resources 
I've learned alot about the PATH variable from [Breanne Boland](https://breanneboland.com/), who wrote the first two articles on this list. 
* [Access & Make Awesome Your PATH System Variable](https://truss.works/blog/2016/2/26/engineer-how-to-access-and-edit-your-path-system-variable)
* [When laziness is efficient: Make the most of your command line](https://stackoverflow.blog/2020/02/12/when-laziness-is-efficient-make-the-most-of-your-command-line/)
* [PATH Definition](http://www.linfo.org/path_env_var.html)
* [How to Modify the Shell Path in macOS Sierra and OSX using Terminal](https://coolestguidesontheplanet.com/add-shell-path-osx/)
* [What is the difference between .bash_profile and .bashrc?](https://apple.stackexchange.com/questions/51036/what-is-the-difference-between-bash-profile-and-bashrc)


## The Filesystem Hierarchy Standard
* The root directory contains folders and files under the forward-slash, `/`.
* The Filesystem Hierarchy Standard defines the organization of the root directory. 
* Most Unix-like operating systems (UNIX, Linux, MacOS, etc.) organize their root directories according to the FHS. 

A few directories in the root directory:
* `/bin`: stands for binary, and contains common commands used by system adminstrators and users 
* `/sbin`: stands for system binaries, andontains root-only commands and commands that pair well with commands in `/bin`
* `/usr`: has some read-only data, and lots of common commands in `/usr/bin`


![](https://upload.wikimedia.org/wikipedia/commons/f/f3/Standard-unix-filesystem-hierarchy.svg) 

<sup>Source: [https://upload.wikimedia.org/wikipedia/commons/f/f3/Standard-unix-filesystem-hierarchy.svg](https://upload.wikimedia.org/wikipedia/commons/f/f3/Standard-unix-filesystem-hierarchy.svg)</sup>

### Resources 
* [Filesystem Hierarchy Standard](https://refspecs.linuxfoundation.org/FHS_3.0/fhs-3.0.html)
* [Wikipedia: Filesystem Hierarchy Standard](https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard)
* [The /bin Directory](http://www.linfo.org/bin.html)
* [Linux Directory Structure explained: /bin folder](https://www.linuxnix.com/linux-directory-structure-explained-bin-folder/)

## The PS1 Variable
* `PS1` is an enviornment variable that creates the default command prompt you see at the beginning of your command line.
* To see the value, run `echo $PS1`.
* Here's an example PS1: 

    `\u@\h:\w\$`

* In the example, the username (`\u`), hostname (`\h`) and working directory (`\w`) come before the dollar sign, and are separated by `@` and `:`.
* On my computer, this PS1 shows up as `kschlesinger@kims-macbook-air:~$` 
* To add colors to your PS1, open your `bash_profile`, `.bashrc` or `.zshrc` and add [ANSI color escape sequences](https://stackoverflow.com/questions/4842424/list-of-ansi-color-escape-sequences) before each section of your PS1. Add an emoji if you'd like. Here's an example: 

    `export PS1="\[\033[36m\]\u\[\033[m\]@\[\033[32m\]\h:\[\033[33;1m\]\w\[\033[m\]\$ 🌵 "` 

* On my computer, this PS1 shows up as `kschlesinger@kims-macbook-air:~$ 🌵 ` with the username in teal, the hostname in green and the working directory in yellow.

### Resources 
* [How to Customize Shell Variable PS1-PS4 on Bash Prompt](https://linoxide.com/how-tos/change-bash-prompt-variable-ps1/)
* [UNIX StackExchange: Colorizing your terminal and shell environment](https://unix.stackexchange.com/questions/148/colorizing-your-terminal-and-shell-environment)
* [My Mac OSX Bash Profile](https://natelandau.com/my-mac-osx-bash_profile/)
* [StackOverflow: List of ANSI color escape sequences](https://stackoverflow.com/questions/4842424/list-of-ansi-color-escape-sequences)
* [Simple Tricks to Improve the Terminal Appearance in Mac OS X](https://osxdaily.com/2013/02/05/improve-terminal-appearance-mac-os-x/)
* [Customize the colors of your Terminal in Mac OS X](http://www.marinamele.com/2014/05/customize-colors-of-your-terminal-in-mac-os-x.html)
