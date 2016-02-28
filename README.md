# Module 1: Terminal and Git

## Overview
In this module, we'll review the basics of using the command line terminal, as well as the foundations of version control using the `git` language, and `GitHub`.  More specifically, we'll cover these skills:

- Navigating your file structure using the command line
- Introduce the syntax of version control using `git`
- Set up `GitHub` as a remote host for your `git` managed projects

** Note **: The terminal instructions are written for mac users, and may require different syntax for other operating systems such as Windows or Linux.  For Windows, you may want to download a command line interface such as [Git Bash] [Powershell](https://www.microsoft.com/en-us/download/details.aspx?id=40855).

## Resources
Here are some helpful outside resources:

- [Introduction to the mac command line](http://www.macworld.co.uk/feature/mac-software/get-more-out-of-os-x-terminal-3608274/)
- [Mac terminal cheatsheet](https://github.com/0nn0/terminal-mac-cheatsheet/wiki/Terminal-Cheatsheet-for-Mac-(-basics-)

## Terminal Use
In order to move forward in this course, there are a few basic commands you'll need to know on the command line.  We'll use the terminal for two primary purposes:

- Running a local web server
- Engaging our version control systems

A simple way to open your terminal is to open your Spotlight Search, type in the word _terminal_, and hit `enter`.  This should open up a terminal window that tell you the **machine** you're using, the **directory** you're currently in, the current **user**, and provides a command prompt for you to type instructions:

![terminal](imgs/terminal.png)

Here is a short-list of commands you'll use to navigate your file structure and create files/directories (a good list is compiled [here](https://github.com/0nn0/terminal-mac-cheatsheet/wiki/Terminal-Cheatsheet-for-Mac-(-basics-))):

| Command  | Function |
| ------------- | ------------- |
| `cd DIRNAME` | change directory to DIRNAME |
| `clear`  | clears terminal  |
| `history`  | shows history of commands |
| `history &#124; grep SEARCH`  | shows history that matches the SEARCH term|
| `ls`  | list contents of diretory  |
| `ls -a`  | list all contents  |
| `mkdir DIRNAME` | make a directory with name DIRNAME|
| `pwd` | print working directory |
| `rm file` | remove (delete) a file |


**A quick tip**: if you start typing a command or a directory name, you can hit the `tab` key to auto-complete the word.  

To practice using these basic commands, see [exercise-1](exercise-1).
