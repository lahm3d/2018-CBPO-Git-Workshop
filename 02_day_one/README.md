# Git Workshop: Day 01

The workshop is designed to introduce Git, a version control system, along with GitHub, a web-hosted service that uses Git for version control. Some of the participants might have heard of these words but they do not know what the hell they are, how the hell do you use them! The goal of this workshop is to provide a gentle introduction to Git and GitHub, so you can start using Git in your daily workflows

![what-is-Git](images/xkcd-git.png)

*source: [xkcd](https://xkcd.com/1597/)*

Here is the outline for day one:
 
1. Introduction: Version Control and GitHub
2. Introduction to Reproducible Science
3. Setting-up Git
4. Git Exercise
5. Working with GitHub (time permitting) 

All the material in this document is either copied or heavily modified from the following sources:
+ [NEON: Version Control Series](https://www.neonscience.org/version-control-git-series)
+ [Software Carpentry: Version Control with Git](https://swcarpentry.github.io/git-novice/)
---

## 01 - Introduction

We are going to use [NEON Version Control Series: GIT 01/Intro to Git Version Control](https://www.neonscience.org/version-control-git-series) tutorial. Instead of rehashing their material, we'll go to their page and follow along.

Take away points:
+ Version control and how it works 
+ Git & GitHub: a distributed version control model
+ GitHub alternatives: GitLab and Bitbucket to name a few. At CBPO, we host our private BitBucket server

## 02 - Introduction to Reproducible Science
The Reproducible Science material was produced by the NEON Project and Dr.Naupaka
Zimmerman. [Click here](https://www.neonscience.org/rep-sci-intro) to access additional material.

[Intro to Reproducible Science](https://neonscience.github.io/slide-shows/intro-reprod-science.html) slide-show will be the reviewed during the workshop. 

## 03 - Setting-up Git

Before we set up Git, let's quickly review the bash commands we learned during our pre-workshop tutorial because we'll be using them in this section:

|Command    |Description                         |
|---        |---:                                |
|`pwd`      |Print working directory             |
|`ls`       |List working directory              |
|`ls`       |Detailed list of working directory  |
|`cd`       |Change directory                    |
|`cd ..`    |Move up directory level             |
|`cp`       |Copy files                          |
|`mv`       |Move files                          |
|`rm`       |Delete files                        |
|`mkdir`    |Make directory                      |

Great now that we have these commands for reference. Let's open up a Git terminal window and start setting up Git. *(Hint: Open SourceTree, and press Shift + Alt + T. This will open a terminal window where you can enter bash commands)*

#### Is Git Installed?
In your terminal window type:

    ~ git --version

#### Setup Global Configurations
Let's configure a few settings on Git such as name, email and text editor:

    ~ git config --global user.name "FirstName LastName"
    ~ git config --global user.email "FLastName@Chesapeakebay.net"
    ~ git config --global color.ui "auto"

The `--global` setting makes sure that any project you work on from this computer will have the above username and email. 

Let's check the settings:

    ~ git config --list

There are several other settings you can configure such as text editor which we are going to ignore for now.

[More information on setting-up Git](https://swcarpentry.github.io/git-novice/02-setup/)

## 04 - Git Exercise
Tea is kinda important, so British Standards Institute laid out a standarized method (ISO 3103) on *"how to document the tea brewing procedure so sensory comparisons can be made"*. Fascinating stuff you can read more about it [here](https://en.wikipedia.org/wiki/ISO_3103). 

In this excercise, we are going take information in a few text files about the ingredients, methodology etc., and make a project titled **ISO-3103_tea-preparation**. Before we get started, we need to download [tea_preparation_data](tea_preparation_data.zip) and unzip it anywhere you can easily access it e.g. desktop. Once you've done that please follow along on the screen and instructions are provided below as well:

1. Navigate to `C:\` and create a folder for Git projects:

        ~ cd /C/
        ~ cd mkdir git-projects
        ~ cd cd git-projects/
        ~ cd mkdir ISO-3103_tea-preparation

    You've created a main folder **git-projects** to store all projects that are Git tracked and then a project folder titled **ISO-3103_tea-preparation**
2. Time to make this folder into a Git repository, so make sure you are in the following directory `/C/git-projects/ISO-3103_tea-preparation`

        ~ pwd
        /C/git-projects/ISO-3103_tea-preparation
        ~ git init
        Initialized empty Git repository in /C/git-projects/ISO-3103_tea-preparation/.git/
        ~ git status
    
    You need to be careful when executing `git init` command that you're in your project specific directory not the main directory. 
    
3. Since our project is empty so let's download some data and create some files. Click here to download the data << insert link >>. Extract the zipped file to the following path: `C:\git-projects\tea_preparation_data`. It is good practice to store data outside of your Git tracked directory; Otherwise, you'll be tracking every single change made to the data and you can easily run out of space.

4. Let's create a `README.md` file using the data in `C:\git-projects\tea_preparation_data`.
    
        ~ pwd
        /C/git-projects/ISO-3103_tea-preparation
        ~ echo "# How to prepare tea" > README.md

    Okay, so we've created a `README.md` file and added a line to it. Now let's check git status:

        ~ git status
        On branch master

        No commits yet

        Untracked files:
        (use "git add <file>..." to include in what will be committed)

            README.md

        nothing added to commit but untracked files present (use "git add" to track)

    This tells me that, an untracked file named `README.md` was created. In order for Git to track the files they need to be added first, so let's add the file:


        ~ git add README
        On branch master

        No commits yet

        Changes to be committed:
        (use "git rm --cached <file>..." to unstage)

            new file:   README.md

    Let's commit the file 

        ~ git commit -m 'Added README.md'
        [master (root-commit) 8af8ece] Added README.md
        Committer: LA <la@email.com>
        Your name and email address were configured automatically based
        on your username and hostname. Please check that they are accurate.
        You can suppress this message by setting them explicitly:

            git config --global user.name "Your Name"
            git config --global user.email you@example.com

        After doing this, you may fix the identity used for this commit with:

            git commit --amend --reset-author

        1 file changed, 1 insertion(+)
        create mode 100644 README.md

    Congrats! You've successfully added a file and commmitted a change.

5. Okay, now let's make some more commits! Open the `README.md` file, and navigate to the data folder i.e. `C:\git-projects\tea_preparation_data\`. Follow the steps below:
    + Open the following file: `01_ingredients.txt`
    + Copy all its contents and paste it into `README.md`
    + On the terminal window check the `git status` and then commit with the following message:
            
            ~ git commit -m "Added ingredients to the readme"   
    + Repeat this for all the files except `05_Fixed_ingredients.txt`, and replace 'ingredients' with appropriate header such as added methodology, sources etc.,
    + **DO NOT** try to copy everything and then commit only once

6. So far we've created a file and made some changes to it. Now let's see how we can look our changes:

        ~ git log

    `git log` command lists all the commits. *Note: commits can be made for a single file or multiple files*

7. Now say we have files in our project that we do not want to track. These are either temporary files or system files that are not important to the project. Let's create some temporary files and an empty folder:

        ~ touch a.dat b.dat c.dat 
        ~ mkdir results/
        ~ touch results/d.txt

    Now let's create a a file titled `.gitignore` and then add the following files and dirs so Git can ignore them.
    
        ~ touch .gitignore

    Navigate to your folder, open `.gitignore` file with your text editor and add the following lines:

        *.dat # to ignore all files that end with .dat
        results/ # to ignore all files in this folder
    
    Final step is to add and commit the `.gitignore` file
    
        ~ git add .gitignore
        ~ git commit -m 'Added files and folders to ignore'
    
    And that's it! You've successfully created a git repo, added files and made commits.

### Workflow review:
1. Add files using `git add abc.txt`
2. Commit files using `git commit -m 'message goes here'`
3. Check status using `git status`

*Sources: [Git-bash cheat-sheet](https://rogerdudler.github.io/git-guide/files/git_cheat_sheet.pdf), [Review sections 3-6 for in-depth explanation](https://swcarpentry.github.io/git-novice/02-setup/)
*

## 05 - Working with GitHub

The workflow above is great when you want to work locally with a single contributor, but if you want to collaborate or share code. You'll want to use services such as GitHub, GitLab or BitBucket. In this section, we will put our tea repository on GitHub so tea enthusiasts can collaborate and share, and while doing so a simple explain Git and GitHub workflow:

1. Open github.com, login and click **New Repository**
2. Under **Repository name** copy and paste name of the git project folder exactly as it is: **ISO-3103_tea-preparation**
3. If you like you can add some description (though it is optional)
4. Set it to **Public**
5. Do not check **Initialize this repository with a README**, and leave other options as it is
6. Click **Create repository**
7. You should see a few options (only the relevant ones are listed):
    + **…or create a new repository on the command line**
    + **…or push an existing repository from the command line**
8. Since we already have some data in our repo, we do not want 'create a new repository on the command line'. All we want to do is upload the existing data in our local Git repo, so all we have to do is add a remote. Adding a remote is basically uploading your local `.git` folder to GitHub.
9. Type the following command to add a remote, and you need to add a remote only once:

        ~ git remote add origin https://github.com/lahm3d/ISO-3103_tea-preparation.git
        ~ git push -u origin master # use this for the firsh push to a bare repo

    In subsequent `push` instances you can use:

        ~ git push origin

    The `push` command pushes the `.git` folder to the GitHub repo page. Now, go to your GitHub and see if we were able to successfully push the changes. 
    
    *Note: `master` is the default local branch git creates, `origin` is the default name of your remote repository. For more detailed explanation read: [Git branching](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell), [Stackoverflow](https://stackoverflow.com/questions/18137175/in-git-what-is-the-difference-between-origin-master-vs-origin-master#18137512)*
