# Git workshop: Day 01

All the material in this document is either copied or heavily modified from the following sources:
+ [NEON: Version Control Series](https://www.neonscience.org/version-control-git-series)
+ [Software Carpentry: Version Control with Git](https://swcarpentry.github.io/git-novice/)


## Workshop purpose and goal
The GIS team at Chesapeake Bay Program for past two years has increasingly relied on programming for automating workflows and developing tools for geospatial analyses. The workshop was envisioned to help GIS team members to provide 

The workshop was designed to introduce Git, a version control systems, which some participants might be aware of but do not know how to get started with it. During the workshop, we will go over how Git works, its features and how to use them, and finally when we have an understanding of those we will look at how we can use it for collaboration. Here is the outline for day one: 

+ What is Git?
+ Reproducible Science
+ Get Git Running: 
    + Command line vs GUI
    + Global configuration
+ Finally doing cool stuff with Git
    + initializing a repo cmd line 
    + git status
    3. Oh shit mistakes happen `rm -rf moons/.git`
    4. mkdir `ISO-3103_the_standardized_method_for_brewing_tea
        tea_methodlogy.md
    5. git status
    6. git add and git commit -- talk about staging area and git diff
    7. Checking changes - using GUI
    8. Ignoring files
+ working with remote repository
    + (online initializing a repo)
    + clone vs fork
    + push changes
    + pull changes

examples:
why git

## 01 - What is Version Control System (VCS) and Git?

A version control system is a software that tracks changes made to any electronic files. It allows for reviewing all changes, reverting to past version or merging information from multiple files. Some examples of version control you might have encountered are embedded in word documents, excel spreadsheets or even Google docs though these are fairly limited. 

Git is a version control system written by Linux Trovalds. It was designed to keep track of files and collaborate with others. As previously mentioned using Git allows you to do the following:
+ Any and all changes are stored for the users to review and revert back
+ Tracks who made what change and when (unlimited undos!)
+ Allows for collaboration between multiple people on the same project
+ Maintain multiple versions of document, code or program in the same file


## **use this to talk about https://www.neonscience.org/version-control-git-series versio ctonrol stuff**

![PlayChanges](https://swcarpentry.github.io/git-novice/fig/play-changes.svg)

[Basics of Git](https://swcarpentry.github.io/git-novice/01-basics/index.html)

*Sources: [Software Carpentry: Version Control with Git](https://swcarpentry.github.io/git-novice/), [Version Control](https://en.wikipedia.org/wiki/Version_control)*

## 02 - Reproducible Science
The Reproducible Science material was produced by the NEON Project and Dr.Naupaka
Zimmerman. [Click here](https://www.neonscience.org/rep-sci-intro) to access additional material.

[Intro to Reproducible Science](https://neonscience.github.io/slide-shows/intro-reprod-science.html) slide-show will be the reviewed during the workshop. 

## 03 - Get Git Running!

Hopefully, everyone remembers some of their bash lesson, if not here is a quick review:

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
|`mkdir`    |Make directory                        |


Okay, now let's open up a Git terminal window. *(Hint: Open SourceTree, and press Shift + Alt + T. This will open a terminal window where you can enter bash commands)*

Once you've the terminal window open, we are going to test out a few Git bash commands:

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
Tea is kinda important, so important that British Standards Institute laid out a standarized method (ISO 3103) on [*"how to document the tea brewing procedure so sensory comparisons can be made"* for the purposes of developing a test that *"would be a taste-test to establish which blend of teas to choose for a particular brand or basic label in order to maintain a consistent tasting brewed drink from harvest to harvest"*](https://en.wikipedia.org/wiki/ISO_3103). Fascinating stuff. 

Great, so we are going take information in a few text files about the ingredients, methodology etc., and make a project titled **ISO-3103_tea-preparation**. Follow along on the screen:

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
    
    And that's it!

### Recap
1. Initialize the repository: `git init`
2. Add files and folders to Git: `git add abc.txt`
3. After making changes to the files and folders, and commit: `git commit -m 'message goes here'`




*Sources: [Git-bash cheat-sheet](https://rogerdudler.github.io/git-guide/files/git_cheat_sheet.pdf), [Review sections 3-6 for in-depth explanation](https://swcarpentry.github.io/git-novice/02-setup/)
*
