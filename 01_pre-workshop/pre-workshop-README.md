# Pre-workshop assignments

This page has all the pre-workshop assignments that need to be completed before the git workshop. Please try to complete the assignments otherwise, it will be difficult to follow along during the workshop. Total estimated time for these assignments should be ~1 hr. The due date is **August 20, 2018**.

**Requirements:** Laptop (*with SourceTree installed*)

**Checklist**
+ Sign up for GitHub Account
+ Install SourceTree (Git GUI client)
+ Brief introduction to bash*
+ Brief introduction to Markdown*
+ Text editor

First two assignments are important for the workshop and rest of them are optional assignments, but reviewing them at least once before the workshop will help you follow along. (**Optional assignments*)

### **(1) GitHub account**
Please sign up for a [GitHub account](https://github.com/join?source=header-home). This should be pretty self-explantory, and of course sign up for the free version.

### **(2) Install SourceTree**
SourceTree is a git GUI client for Windows and Mac created by Atlassian.
* Download [SourceTree](https://www.sourcetreeapp.com/) and click download
* SourceTree does not require admin rights, so you can install the client without requesting permission from IT helpdesk
* You will need an Atlassian account to complete the installation, so when you get to a **Log in to your Atlassian account** page
click on **Go to My Atlassian**, and click on **create a new account** (or you can sign up from the [website](https://id.atlassian.com/signup?) )
* Installation options:
    * Skip the **Connect an account** prompt, we will add the account manually
    * Only install git, do not install mercurial
    * Also, skip the following prompts: **Remotes** and **Starting repositories**
* [Install SourceTree](https://confluence.atlassian.com/get-started-with-sourcetree/install-sourcetree-847359094.html) documentation has detailed steps

### **(3) Intro to Bash**
Git can used through command line and GUI interface. Originally, git was written for Linux/GNU operating systems which use a command line shell known as `bash`, when git was made available on windows the git shell commands were packaged as *Git Bash* along with additional tools that allows users to use similar commands found on Linux operating systems. In this workshop, we will emphasize on Git Bash, but will cover GUI options using using SourceTree. However, before you can use git bash you will need to learn some bash basics, the following assignment will cover basic bash commands:

* The goal here is to gain basic knowledge of bash commands to navigate between folders, create and move files and folders, delete items etc.,
* Please review this (Extremely Short Introduction to Bash0[http://www.karlin.mff.cuni.cz/~hron/fenics-tutorial/bash/doc.html]. *(Note: only need to focus on sub-section titled **Basic shell commands**)*
* [More detailed explanations](https://www.guru99.com/must-know-linux-commands.html) of bash commands
* Once you've reviewed these commands, you can try them out by starting SourceTree, and pressing `Shift + Alt + T`. This should open a terminal window where you can enter bash commands. Also, give it a few minutes for it to start up, and on your terminal window you should see the following text in following format:  `username@computer name MINGW32 ~`

        lahmed@USGS1 MINGW32 ~

### **(4) Markdown**
Markdown (MD) is a markup language that allows people to add simple formatting syntax to plain text. It allows users to easily create readable and writable documents with formatting that can be converted to HTML. This is one the reasons why it is a popular format for creating `README.md` files. In fact, this tutorial was written using markdown. Learning Markdown is not a requirement for this workshop, but it will be used during the workshop. If you are intersted you can complete [Introduction to Markdown tutorial](https://www.markdowntutorial.com/) in ~10 minutes


### **(5) Text Editor**
All you need is a basic text editor (notepad) and most people should have Notepad++, Sublime, or VisualStudio Code. The latter ones are slightly more powerful and if there's time we'll discuss git integration into text editors