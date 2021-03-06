# Module 1: Terminal and Git

## Overview
In this module, we'll review the basics of using the command line terminal, as well as the foundations of version control using the `git` language, and `GitHub`.  More specifically, we'll cover these skills:

- Navigating your file structure using the command line
- Introduce the syntax of version control using `git`
- Set up `GitHub` as a remote host for your `git` managed projects

**Note**: The terminal instructions are written for mac users, and may require different syntax for other operating systems such as Windows or Linux.  For Windows, you may want to download a command line interface such as [Git Bash](https://git-for-windows.github.io/) or [Powershell](https://www.microsoft.com/en-us/download/details.aspx?id=40855).

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Contents**

- [Resources](#resources)
- [Terminal Use](#terminal-use)
  - [Basic Commands](#basic-commands)
  - [Running a local server](#running-a-local-server)
- [Version control](#version-control)
  - [Git](#git)
  - [GitHub](#github)
- [Hosting](#hosting)
  - [UW Student Hosting](#uw-student-hosting)
  - [Hosting on GitHub](#hosting-on-github)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Resources
Here are some helpful outside resources:

- [Introduction to the mac command line](http://www.macworld.co.uk/feature/mac-software/get-more-out-of-os-x-terminal-3608274/)
- [Mac terminal cheatsheet](https://github.com/0nn0/terminal-mac-cheatsheet/wiki/Terminal-Cheatsheet-for-Mac-(-basics-))
- [Try Git](https://try.github.io/levels/1/challenges/1): An interactive tutorial for learning `git`
- [Git Documentation](https://git-scm.com/documentation)
- [Setting up git](https://help.github.com/articles/set-up-git/) (with GitHub)
- [Git command line reference](https://git-scm.com/docs)
- [Git Introductory Videos](http://git-scm.com/videos)
- [Git cheatsheet](https://training.github.com/kit/downloads/github-git-cheat-sheet.pdf)
- [Hosting with GitHub Pages](https://help.github.com/articles/creating-project-pages-manually/)
- [UW Student Hosting](http://itconnect.uw.edu/connect/web-publishing/shared-hosting/activating-shared-web-hosting/)
- [UW SSH Connection](https://itconnect.uw.edu/connect/web-publishing/shared-hosting/ssh/)

## Terminal Use
In order to move forward in this course, there are a few basic commands you'll need to know on the command line.  We'll use the terminal for two primary purposes:

- Running a local web server
- Engaging our version control systems

A simple way to open your terminal is to open your Spotlight Search, type in the word _terminal_, and hit `enter`.  This should open up a terminal window that tell you the **machine** you're using, the **directory** you're currently in, the current **user**, and provides a command prompt for you to type instructions:

![terminal](imgs/terminal.png)

### Basic Commands

Here is a short-list of commands you'll use to navigate your file structure and create files/directories (a good list is compiled [here](https://github.com/0nn0/terminal-mac-cheatsheet/wiki/Terminal-Cheatsheet-for-Mac-(-basics-))):

| Command  | Function |
| ------------- | ------------- |
| `cd DIRNAME` | change directory to DIRNAME |
| `clear`  | clears terminal  |
| `history`  | shows history of commands |
| <code>history &#124; grep SEARCH</code>  | shows history that matches the SEARCH term|
| `ls`  | list contents of diretory  |
| `ls -a`  | list all contents  |
| `mkdir DIRNAME` | make a directory with name DIRNAME|
| `pwd` | print working directory |
| `rm file` | remove (delete) a file |


**Some quick tips**:

- If you start typing a command or a directory name, you can hit the `tab` key to auto-complete the word.  
- You can use the tilde (`~`) to signify the home directory of the logged in user.  In other words, instead of typing `cd /Users/username/Documents`, you can just type `cd ~/Documents`.  This both saves time, and makes it easier to write code that runs on multiple machines.
- To change directory to the parent directory one level above the current directory, use the `..` shorthand.  For example, to enter a sibling directory, you may say `cd ../sibling`.   

To practice using these basic commands, see [exercise-1](exercise-1).

### Running a local server
In addition to managing our files, we'll use the terminal to run a local web server.  While this may sound involved, it's really only one line of code:

```
# Start running a local server in your current directory
python -m SimpleHTTPServer 8080
```
The files in your current directory will then be accessible in your web browser at `localhost:8080`.

If you're on windows, you may prefer to install a GUI tool like [WAMP](http://www.wampserver.com/en/).

## Version control
This is a brief review of basic version control operations using `git` and `GitHub`.  When programmatically building interactive data visualizations, it's imperative that you're able to track changes to your code, share your code, and collaboratively code with other developers.  We'll cover collaboration in a later module, but if you don't feel comfortable using the basics of these systems, **make sure to practice now**.

### Git
`Git` is a free and open-source version control software that provides you with a set of command line tools for tracking changes to your files.  All of the files in a project directory (referred to as a `repository`, or `repo`) are tracked by a hidden `.git` file in the root of the project.  You can initiate a repository with the `git init` command.  

Git allows you to roll back to a previous snapshot of your project called a `commit`.  When you want to take a snapshot of your work, you'll need to `add` your the changes to your files to a **staging area**.  You can think of a staging area (literally) like a staging area.  The changes that you want to be included in your next snapshot need to be put on stage in order to be captured by the `commit`.  Each time you take a snapshot (`commit`), you'll need to include a short message that describes the set of changes.  These steps fit together as follows:

![git-process](imgs/git-process.gif)

Here is additional information on each (of these) `git` commands (note, this **_is not_** a full list -- see [documentation](https://git-scm.com/docs)):

| Command  | Function |
| ------------- | ------------- |
| `git init` | Initialize a new repository in the current directory|
| `git status`  | Tells you the current status of the git repository. It also often tells you what commands to execute next. If you are in doubt, execute git status and read what it says carefully!  |
| `git add FILE-NAME` or `git add .`  | Adds a file or files (`.`) to the staging area. All changes to those files will be included in the next commit. |
| `git commit -m "Description"`  | Commits all changes to all files currently in the staging area to the repository.|


### GitHub
The `git` process described thus far all happens on your local machine.  In order to share our code and collaborate with other, we'll need a publicly accessible location where we can store our files -- that's what GitHub is for.  

GitHub is the most popular open-source web-based repository hosting service.  In addition to providing a great UI on top of a server that hosts your repositories, GitHub has a number of additional features such as issue tracking, wiki pages, and notifications that make it a great collaboration tool.  

The important thing to keep in mind is that GitHub doesn't just store the files in your repository -- it stores the **entire database of changes** to the files, allowing other developers to view the files at an earlier point in time.  

Here is an example of one workflow you may choose when working with a project.  First, you may want **your own copy** of a repository on GitHub.  To create your own copy, you'll simply click the **fork** button in a repository:

![fork-button](imgs/fork.png)

That will create a copy of the **entire repo** on your GitHub account.  In order to start working on the files, you'll need to get them on your computer.  To do so, you will clone **your forked repository** (_not_ the original one) to your machine.  You can easily get the url by clicking the clipboard icon:

![copy](imgs/copy.png)

Then, on your terminal, you could use the `git clone` command described below.  Here is a diagram of the full process:

![git-process-full](imgs/git-process-full.gif)


Here are additional `git` commands that allow you to interact easily with GitHub:

| Command  | Function |
| ------------- | ------------- |
| `git clone REPO-URL` | Creates a new copy of a source repository, which typically exists on a remote server. Use this when you want to clone down a GitHub repository. This command will create a new subdirectory with the same name as the source repository. |
| `git push origin master`  | Pushes all commits on the `master` branch made since the last push to another repository (`origin`), typically across the network (e.g., to GitHub)  |
| `git pull`  | Pulls all commits made since the last pull from another repository, and attempts to merge those changes into your current files. |
| `git config` | Configure your GitHub account. You should run `git config --global user.name "Your Full Name" and `git config --global user.email your-github-email` to initially set up. |

To practice using these basic commands, see [exercise-2](exercise-2).

## Hosting
Once you build an interactive data visualization, you'll obviously want some way to share it with the world. In order to accomplish this, you will need to **host** your code on a web-server, which will provide you with a URL at which you (and others) can access your project. There are myriad options for web-hosting, two of which we'll describe here.

### UW Student Hosting
If you are a UW student, the University provides free student/staff/faculty web-hosting. Using the hosting services is quite painless once you get it set up.

1. [activate your web-host](http://itconnect.uw.edu/connect/web-publishing/shared-hosting/activating-shared-web-hosting/), which you do online through the UW-IT website.
2. [Connect to your host](https://itconnect.uw.edu/connect/web-publishing/shared-hosting/ssh/), which you can easily do on your terminal (if you're a mac user), or via an SSH client such as [PuTTy](http://www.chiark.greenend.org.uk/~sgtatham/putty/). Connect via the terminal using the following command:

```
# Replace NETID with your uw net id and SERVER with the name of your server (dante, or homer)
ssh NETID@SERVER.u.washington.edu
```

3. Once you've connected to your server, navigate to the folder that holds your publicly availabe projects, and pull down the project from GitHub:

```
# Navigate to public directory
cd public_html

# Clone down the project (if it's the first time)
git clone https://github.com/USER-NAME/PROJECT-NAME.git

# Whenever you make changes, simply pull down the changes
git pull https://github.com/USER-NAME/PROJECT-NAME.git
```

### Hosting on GitHub
An awesome features of GitHub that we haven't discussed is that it will actually host webpages for you auto-magically! In particular, it will render an `index.html` file on a GitHub Pages branch with name `gh-pages`. So, all we need to do to get this HTML page up on the web for **anyone** to see is create a branch called `gh-pages` and push it up to GitHub. Here's the syntax you'll want to use in your terminal:

```
# Get into your repository
cd project-name

# Add and commit changes to your current (master) branch
git add .
git commit -m "Commit message goes in here"

# Create and checkout a new branch called 'gh-pages'
git checkout -b gh-pages

# Push all changes (including your new branch) up to GitHub
git push --all
```
You should now see your `index.html` file up on the web at `your-username.github.io/project-name`. Keep in mind, if you make change to your `master` branch, you'll need to make those same changes in your `gh-pages` branch in order for them to be reflected in the live version hosted by GitHub.
