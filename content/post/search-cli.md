---
title:      2 Ways to Search Your Command Line History 
date:       2019-10-02
description:    Two techniques to find and run a command you've used in the past
draft: false
author: Kim Schlesinger 
---

Sometimes you have to execute a complex command that you've used in the past. Instead of using the up-arrow key to scroll through your previous commands one at a time, here are two ways you can run a command without typing it again. 

## 1. The `history` command
* Type `history` and hit `enter` 
* Find the number of the command you want to run again
* Use one of the following commands:
    * `!213` runs command number 213
    * `!!` runs the last command 
    * `sudo !!` reruns the last command command as sudo 

## 2. Reverse Search
* Use `control + r` and the type one or two words from the command you’re looking for 
* Keep hitting `control + r` to go back through the history and find the exact command you're looking for
* Once you've found what you're looking for, hit `tab` to autocomplete the entire command
* Hit `enter` to run the command
