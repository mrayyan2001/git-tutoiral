# Git & GitHub - Part 1

## What is Git?

- version history for code.

## Hot to install Git?

### Check if Git is already installed

```bash
git --version
```

### Install Git on Ubuntu

```bash
sudo apt-get update
sudo apt-get install git
```

### Install Git on Windows

1. Download Git from [git-scm.com](https://git-scm.com)
2. Walk through the installation process

## Git Setup

### Set up username and email

```bash
git config --global user.name "name"
git config --global user.email "email"
```

### Change default branch name

```bash
git config --global init.defaultBranch <name>
```

## Creating a verion

### Initialize a Git repository

```bash
git init
```

### Check the status of the repository

```bash
git status
git status -s # shows the status in a short way
```

### Add files to the staging area

- Staging area is a place where we can add files before committing them. (Pick which changes wan in the next version/commit)

```bash
git add <file> # add a single file
git add . # add all files except those in .gitignore (we can also use * instead of .)
```

### Commit changes

- verion = commit
- version history = commit history

```bash
git commit -m "message" # -m is for message and description is the message
git commit -m "message" -m "description" # the first message is the title and the second is the description (optional)
```

If you don't add a message, it will open a text editor where you can write the message.

### Check the commit history

```bash
git log # shows the commit history
git log --all # shows the commit history of all branches
git log --oneline # shows the commit history in one line
git log --oneline --graph # shows the commit history in one line with a graph
```

### Commit to the previous commit

- amend = change

```bash
git commit --amend -m "message" # amend the previous commit
```

## Git Visualizing and Git Fundamentals

- It's the same as `git status` but in a visual way.
- Based on the code editor you are using, you can see the changes in the editor.

## Staging Area and Working Area

### Working Area -> Staging Area -> Repository

- To move a file from the working area to the staging area, we use `git add <file>`.
- To move a file from the staging area to the repository, we use `git commit -m "message"`.

We may have the same file in the working area and the staging area, but with different content.

### Tracking and Untracking Files

- To track a file, we need to add it to the staging area and commit it.
- To untrack a file, we need to remove it from the staging area and commit it.

### Take file out of the staging area

```bash
git reset <file> # take the file out of the staging area
git restore --staged <file> # this is the same as the previous command
```

### Untrack a file

```bash
git rm --cached <file> # untrack a file
```

### Undo changes

```bash
git checkout -- <file> # undo changes in a file
git restore <file> # this is the same as the previous command
```

- this work for files that are not in the staging area.
- We can use combination of `git restore` and `git reset` to go to the last commit.

## Previous Commit

### Go to the previous commit

```bash
git checkout <commit-hash> # go to a specific commit
git checkout HEAD~1 # go to the previous commit
git checkout - # Undo the previous command
git checkout <commit-hash> <file> # go to a specific commit for a specific file
```
- To go back to the latest commit, we can use `git checkout master`.
- We can make update on the previous commit and commit it again. This will create a new branch. use `git log --all --graph` to see the branches.

## Summary

### Create a version

- `git init`
- `git status`
- `git add <file>`
- `git commit -m "message"`

### Configure Git

- `git config --global user.name "name"`
- `git config --global user.email "email"`

### View the commit history

- `git log --all --graph`
- `git checkout <commit-hash>`
- `git checkout <branch-name>`

### Resoter to the previous commit

- `git checkout <commit-hash|branch-name|HEAD~1 <file|directory>`
- `git commit -m "message"`

## Extra Features

### Aliases

```bash
git config --global alias.<alias-name> <command>
```
#### Examples
- `git config --global alias.cm commit -m`
- `git config --global alias.co checkout`
- `git config --global alias.lg "log --all --graph"`

### Gitignore

All the files/folders that we don't want to track should be added to the `.gitignore` file.

- Create a `.gitignore` file in the root directory of the project.
- Add the files/folders that we don't want to track to the `.gitignore` file.

### Remove git

```bash
rm -rf .git # remove the .git folder
```