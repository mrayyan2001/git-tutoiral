# Git & GitHub Full Course

Git is a free, open-source distributed version control system used to track changes in source code during software development. It helps manage collaboration among teams, allowing users to track who made changes, why, and when.

## General Commands that we will use in this course

- `cd` : Change directory
- `ls` : List directory
- `pwd` : Print working directory
- `touch` : Create a file
- `mkdir` : Create a directory
- `rm` : Remove a file
- `rmdir` : Remove a directory
- `cp` : Copy a file
- `mv` : Move a file/directory or rename a file/directory
- `cat` : Concatenate and display the content of a file
- `tree` : Display the directory structure in a tree format

## What is Git?

Git is a version control system that keeps track of changes in code over time, enabling developers to manage and track version history.

## Why Use Git?

Git is necessary for collaboration within a team. It allows multiple developers to work on the same project at the same time. It also allows you to keep track of changes made to your code and revert back to previous versions if needed.

## Installing Git

There are several ways to install Git on your system. You can download it from the official website or use package managers like `winget`, `brew`, or `apt-get` to install it.

You can check if Git is already installed on your system by running the `git --version` command in the terminal.

### Installing Git from the Official Website

To install Git, you can download it from the official website [https://git-scm.com/](https://git-scm.com/). Once downloaded, you can follow the installation instructions provided on the website.

### Installing Git using Package Managers

- **For Windows**: You can install Git using the `winget install -e --id Git.Git` command in the Windows Terminal.
- **For macOS**: You can install Git using the `brew install git` command in the Terminal.
- **For Linux**: You can install Git using the `sudo apt-get install git` command in the Terminal.

## Configuring Git

After installing Git, you need to configure it with your name and email address. This information will be used to identify you as the author of the code changes you make.

### There are three levels of configuration in Git

1. System-Level: Applies to all users on the system. (--system)
2. Global-Level: Applies to the current user. (--global)
3. Local-Level: Applies to the current repository. (--local)

### Setting Up the main configuration

- `git config --global user.name` "<Your-Full-Name>" -> set your name
- `git config --global user.email` "<Your-Email>" -> set your email
- `git config --list` -> list all configurations
- `git config --global core.editor "code --wait"` -> set Visual Studio Code as the default editor
- `git config --global --edit` -> open the global configuration file in the default editor
- `git config --global init.defaultBranch <name>` -> set the default branch name (the most common is `main`)

## Git Initialization

To start using Git in a project, you need to initialize a Git repository in the project directory. This creates a `.git` directory that stores all the version history and configuration files.

`git init` -> initialize a Git repository in the current directory

## Git Status

The `git status` command shows the current status of the repository, including untracked files, modified files, and staged files.

`git status` -> show the current status of the repository

## Git Add

The `git add` command adds changes in the working directory to the staging area. It prepares the changes to be committed in the next step. (It's like adding items to a shopping cart before checkout.) or you can say it's like a checkpoint.

The staging area lets you select which changes to include in the next commit.

`git add <file>` -> add a specific file to the staging area
`git add .` -> add all files except those listed in `.gitignore` to the staging area (It's not recommended to use this command, because it adds all files, including those that you don't want to commit)

## Git Commit

The `git commit` command saves the changes in the staging area to the local repository. It creates a new commit with a unique commit ID, author, date, and commit message. (It's like checking out from a store after adding items to the shopping cart.) or you can say it's like a snapshot.

A commit represents a version of your code. It captures the current state of the repository and saves it in the version history.

- `git commit -m "Commit message"` -> commit changes with a message
- `git commit -m "Commit message" -m "Description"` -> commit changes with a message and description
- `git commit` -> commit changes with a message in the default editor

## Git Log

The `git log` command shows a list of commits in the repository, including the commit ID, author, date, and commit message. (It's like viewing the order history in an online store.)

`git log` -> show the commit history

### Useful Flags for `git log`

- `--oneline` -> Condensed commit history
- `--graph` -> Graphical commit history
- `--all` -> Show all branches

## Git Remote

The `git remote` command manages connections to remote repositories. It allows you to add, remove, and view remote repositories. 


