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

- `git init` -> initialize a Git repository in the current directory
- `git rm .git/ -rf` -> remove the `.git` directory to uninitialize the repository

## Git Status

The `git status` command shows the current status of the repository, including untracked files, modified files, and staged files.

`git status` -> show the current status of the repository

## Git Add

Workflow: Working Area → Staging Area → Repository

- Move files from working to staging with `git add`.
- Move files from staging to the repository with `git commit`.

The `git add` command adds changes in the working directory to the staging area. It prepares the changes to be committed in the next step. (It's like adding items to a shopping cart before checkout.) or you can say it's like a checkpoint.

The staging area lets you select which changes to include in the next commit.

- `git add <file>` -> add a specific file to the staging area
- `git add .` -> add all files except those listed in `.gitignore` to the staging area (It's not recommended to use this command, because it adds all files, including those that you don't want to commit)
- `git rm --cached <file>` -> Untrack a file
- `git reset <file>` or `git restore --staged <file>` -> remove a file from the staging area

## Git Ignore

The `.gitignore` file is used to specify files and directories that should be ignored by Git. It allows you to exclude files like log files, build artifacts, and temporary files from version control.

- Create a `.gitignore` file in the root directory of the repository.
- Add the files and directories you want to ignore to the `.gitignore` file.

## Git Commit

The `git commit` command saves the changes in the staging area to the local repository. It creates a new commit with a unique commit ID, author, date, and commit message. (It's like checking out from a store after adding items to the shopping cart.) or you can say it's like a snapshot.

A commit represents a version of your code. It captures the current state of the repository and saves it in the version history.

- `git commit -m "Commit message"` -> commit changes with a message
- `git commit -m "Commit message" -m "Description"` -> commit changes with a message and description
- `git commit` -> commit changes with a message in the default editor
- `git commit --amend` -> amend the last commit (change the commit message or add more changes to the last commit)

## The Perfect Commit

- Add the right changes.
  - The goal is to create a commit that makes sense—one that only includes changes from a single topic. Avoid cramming all your current local changes into the next commit.
  - Selectivity is Key: Being selective and carefully deciding what should go into the next commit is crucial. This approach separates different topics, making it easier to understand both for your colleagues and yourself in the future.
  - Using the Staging Area: Git's staging area concept is helpful here. It allows you to select specific files or even parts of those files for the next commit. You can leave others for future commits.
- Compose a good commit message.

1. git status to see the changes.
2. git add <file> to stage the changes. You can also use git add . to stage all changes, but we need to add just the right changes.
3. git diff to see the changes that are staged. or git diff <file> to see the changes in a specific file. This command shows the difference between the working directory and the staging area.
4. git add -p to interactively stage changes. This command allows you to select parts of a file to stage. (You might see two parts or chunks of changes. Let's say the first one belongs to the next commit's topic, but not the second one.)

## The Perfect Commit Message

Subject: concise summary of what happened.

body: more detailed explanation.

- what is now different?
- what's the reason for the change?
- Is there anything to watch out for/ anything particularly remarkable?

git commit will open your default editor to write the commit message.

Subject Line: Write something concise, less than 80 characters if possible. The subject should be a brief summary of what happened.

Body of the Message: After an empty line, Git knows you're writing the body of the message, where you can provide a detailed explanation. Answer questions like:

- What's now different than before?
- What's the reason for the change?
- Is there anything to watch out for?

A commit message is a brief description of changes made in a commit. Conventional Commits is a commit message convention that makes it easier to understand the changes in a repository.

Example of a conventional commit message: `feat: add new feature`

- The message consists of a type and a description.
- The type can be feat, fix, docs, style, refactor, test, or chore.
- The description is a brief summary of the changes made.
- The message is written in the present tense.

## Git Log

The `git log` command shows a list of commits in the repository, including the commit ID, author, date, and commit message. (It's like viewing the order history in an online store.)

`git log` -> show the commit history

Useful Flags for `git log`

- `--oneline` -> Condensed commit history
- `--graph` -> Graphical commit history
- `--all` -> Show all branches

## Git Alias

Git aliases are shortcuts for Git commands. They allow you to create custom commands that are easier to remember and type.

- `git config --global alias.<alias-name> <command>` -> create a Git alias
- `git config --global alias.<alias-name>` -> show the alias command
- `git config --global --unset alias.<alias-name>` -> remove a Git alias

Useful Git Aliases

- `git config --global alias.lg "log --oneline --graph --all"` -> create an alias for a condensed graphical commit history

## Git Remote

The `git remote` command manages connections to remote repositories. It allows you to add, remove, and view remote repositories.

Remote repositories are versions of your project that are hosted on the Internet or network. They can be used to collaborate with other developers and share code.

Example of a remote repository: GitHub, GitLab, Bitbucket

### Create a Remote Repository on GitHub

1. Go to [GitHub](www.github.com) and log in to your account.
2. Click on the + icon in the top right corner.
3. Select New repository.
4. Enter the repository name.
5. Add a description.
6. Choose public or private.
7. Initialize with a README file or not.
8. Click Create repository.
9. Copy the repository URL.

### Add a Remote Repository

- `git remote add origin <repository-url>` -> add a remote repository (`origin` is the default name for the remote repository. You can use any name you like.)
- `git remote set-url origin <URL>` -> change the URL of the remote repository
- `git remote` -> list remote repositories
- `git remote -v` -> list remote repositories with URLs (verbose)
- `git remote remove origin` -> remove a remote repository

We will have two repositories:

- Local repository: on your computer.
- Remote repository: on GitHub.

## Git Push

The `git push` command to send changes from the local repository to the remote repository. It updates the remote repository with the latest changes.

`git push -u origin main` -> push changes to the remote repository (`-u` sets the upstream branch to track the remote branch it's stands for `--set-upstream`)

you can use `-f` to force push the changes to the remote repository. It's not recommended to use it because it can overwrite changes in the remote repository.

Before pushing changes to the remote repository, make sure to pull the latest changes from the remote repository to avoid conflicts.

### Personal Access Token for GitHub Authentication

You need to create a personal access token to authenticate with GitHub when pushing changes to a remote repository. You can create a token in your GitHub account settings.

1. Go to GitHub.
2. Click on your profile.
3. Go to `Settings`.
4. Click on `Developer settings`.
5. Click on `Personal access tokens`.
6. Click on `Generate new token`.
7. Enter the password.
8. Select the scopes.
9. Click on `Generate token`.
10. Copy the token.
11. Use the token as a password.

## Git Pull

The `git pull` command fetches changes from the remote repository and merges them into the local repository. It updates the local repository with the latest changes from the remote repository.

- `git pull origin main` -> pull changes from the remote repository (if you set the upstream branch with `-u`, you can use `git pull` without specifying the remote and branch)
- Setting the upstream branch: `git branch --set-upstream-to=origin/main main` or `git branch -u origin/main main` or `git push -u origin main`

`git pull` = `git fetch` + `git merge`

1. `git fetch origin main` -> fetch changes from the remote repository without merging them into the local repository
2. `git merge origin/main` -> merge changes into the local repository

## Git Clone

The `git clone` command creates a copy of a remote repository on your local machine. It downloads the repository files and sets up a local repository with the same version history. You don't need to initialize a Git repository before cloning a remote repository.

- `git clone <repository-url>` -> Clone the repository to the current folder (the repository name will be the folder name)
- `git clone <repository-url> <folder-name>` -> Clone the repository to a specific folder

## GitHub Codespaces

GitHub Codespaces is an online development environment that allows you to code directly in your browser. It provides a full-featured development environment with a code editor, terminal, and debugger.

To create a Codespace:

1. Go to your GitHub repository.
2. Click on the `Code` button.
3. Click on `Code Spaces`.
4. Click on `New code space`.

## Git Branches

Branches in Git are used to work on different versions of the code simultaneously. They allow you to isolate changes and work on new features without affecting the main codebase.

- Branching = work on multiple features at the same time
- the new branch take a copy of the current branch and you can work on it without affecting the main branch
- you can merge the new branch back to the main branch when you are done

Imagine you are working on a large feature that requires multiple commits. Suddenly, your manager asks you to fix a critical bug. You don't want to mix your incomplete feature code with the bug fix. Branching solves this by allowing you to:

1. Create a new branch for your feature.
2. Switch back to the main branch to apply the bug fix.
3. Continue working on your feature without interference.

- `git branch` -> list all branches
- `git branch <branch-name>` -> create a new branch
- `git branch -d <branch-name>` -> delete a branch
- `git branch -D <branch-name>` -> force delete a branch
- `git branch -M <branch-name>` -> rename the current branch

## Git Checkout

The `git checkout` command is used to switch between branches in Git. It allows you to move between different branches and work on different versions of the code. You can also use it to create a new branch and switch to it in one step. and you can use it to switch between commits.

- `git checkout <branch-name>` -> switch to a branch
- `git checkout -b <branch-name>` -> create a new branch and switch to it
- `git checkout <commit-id>` -> switch to a commit
- `git checkout -b <branch-name> <commit-id>` -> create a new branch from a commit and switch to it
- `git checkout -- <file>` or `git restore <file>` -> discard changes in a file
- `git checkout .` -> discard changes in all files
- `git checkout HEAD~1` -> switch to the previous commit
- `git checkout -` -> switch to the previous branch

Summary: `git checkout <commit-hash|branch-name|HEAD~1> <file|directory>` -> switch to a commit, branch, or previous commit and restore a file or directory

## Git Merge

The `git merge` command is used to combine changes from different branches. It merges the changes from the source branch into the target branch. It creates a new commit with the combined changes.

Merging combines changes from different branches into one. This is useful when you finish a feature and want to integrate it back into the main branch.

The result of a merge is a combination of the changes from both branches.

The merge go to the branch that you are working on. So if you are working on the new branch, the merge will go to the new branch and not the main branch. You have to switch to the main branch and merge the new branch to the main branch.

- `git merge <branch-name>` -> merge changes from a branch into the current branch
- `git merge --abort` -> abort the merge and restore the previous state (stop the merge process)

## Merge Conflicts

- `git merge`, `git rebase`,` git pull`, `git cheary-pick` or `git stash apply` can cause merge conflicts.
- Git will clearly notify you when a conflict occurs. Use git status to identify unmerged paths.
- ignore merge conflicts: `git merge --abort` or `git rebase --abort`.
- continue the merge: `git add <file>` then `git commit`. or `git merge --continue`. or `git rebase --continue`. after resolving the conflict.
- How to solve the conflict? simply cleanup the file and remove the conflict markers `<<<<<<<`, `=======`, `>>>>>>>`.

A merge conflict occurs when Git cannot automatically combine changes from different branches, typically because the same part of the code was modified differently.

When a merge conflict occurs, Git marks the conflicting lines in the affected files. You need to resolve the conflict manually by editing the files and choosing which changes to keep.

1. Follow the same merging steps as before.
2. If a conflict occurs, Git will pause the merge and tell you which files have 2. conflicts.
3. Open the conflicting files in your code editor.
4. Manually resolve the conflicts.
5. Add the resolved files `git add .`
6. Continue the merge `git merge --continue` or `git commit -m "Merge message"`
7. Remove the new branch `git branch -d new-branch-name`

## Feature Branch Workflow

A professional workflow used by teams to manage code changes. Involves creating feature branches, uploading them to GitHub, and performing code reviews via pull requests.

1. Create a feature branch. -> `git checkout -b feature-branch-name`
2. Developing the Feature -> make commits
3. Upload the feature branch to GitHub. (all the team members can see our code) -> `git remote add origin <url>` -> `git push origin feature-branch-name`
4. Create a `pull request`. (do code review)
   1. Go to your GitHub repository.
   2. Click on Pull Requests and then New Pull Request .
   3. Compare new-feature with master.
   4. Add a description and submit the pull request.
5. Code Review and Merging (merge happens on GitHub) -> on GitHub click on `pull request` -> `the request` -> `merge pull request` -> `merge pull request` -> `confirm merge`
   1. Teammates review the code and leave comments if necessary.
   2. Once approved, merge the pull request into master.
6. Syncing Local Repository -> `git checkout main` -> `git pull origin main`

## Merge Conflicts in feature branches workflow (pull request)

suppose we are working on two different branches and we want to merge them to the main branch. If there is a conflict, we have to resolve it in the main branch and not in the feature branch.

1. push the two branches to GitHub
2. create a pull request for the first branch
3. create a pull request for the second branch
4. if there is a conflict, resolve it in the main branch you have different options to resolve the conflict
   1. merge on github using web editor
   2. merge on your local machine using command line
      1. `git checkout main`
      2. `git pull origin main`
      3. `git checkout new-branch-name`
      4. `git merge main`
      5. resolve the conflict
      6. `git add .`
      7. `git commit -m "merge message"` or `git merge --continue`
      8. `git push origin new-branch-name`

## Branching Strategies

### A Written Convention

Agree on a Branching Worflow in Your Team

- Git allows you to create branches - but it doesn't tell you how to use them!
- You need a written best practice of how work is ideally structured in your team - to avoid mistakes & collisions.
- It highly depends on your team / team size, on your project, and how you handle releases.
- It helps to onboard new team members ("this is how we work here").

If you work in a team, establish a clear convention on how to work with branches and document it. This helps avoid mistakes and collisions and aids in onboarding new team members.

### Types of Branches

- Long-Running Branches: These exist throughout the project's lifecycle, such as `main` or `master`. Other examples include `develop` or `production`.
- Short-Lived Branches: Created for specific purposes and deleted after integration. Examples include `feature branches`, `bug fixes`, or `experiments`.

Commit never directly to main or master! it's make through integration (merge or rebase) from a feature branch or pull request. Short-lived will be deleted after integration.

### Popular Branching Strategies

- GitHub Flow: Extremely lean and simple. Only one long-running branch (`main`), and all active work is done in short-lived branches.
- Git Flow: Offers more structure and rules. Includes a `main` branch reflecting production state, a `develop` branch, `feature` branches, `release` branches, and `hotfix` branches.

## Pull Requests

Pull requests are not a core Git feature but are provided by Git hosting platforms like GitHub, GitLab, Bitbucket, etc. They facilitate communication and code review.

### Why Use Pull Requests?

- Code Review: Have a second pair of eyes look over your code.
- Contributing to Repositories: Contribute to repositories you don't have direct access to by forking and opening pull requests.

### Example: Using Pull Requests on GitHub

1. Fork the repository. This creates a copy of the repository in your GitHub account.
2. git clone <forked-repository-url> to clone the repository to your local machine.
3. git checkout -b <branch-name> to create a new branch.
4. Make changes, commit them, and push the branch to your forked repository.
5. Open a Pull Request: On GitHub, propose integrating your changes into the original repository.

- Alwyas before `push` make sure to `pull` to avoid conflicts.
- `git pull origin main` this work if you are work on the original repository.
- if you forked the repository and you want to update your forked repository with the original repository, to do that you need to add the original repository as a remote repository. git remote add upstream <original-repository-url> then `git pull upstream main` to pull the changes from the original repository to your forked repository. or you can use `git fetch upstream` then `git merge upstream/main`.

## Merge vs Rebase

### Merge

When Git performs a merge, it looks for three commits:

- Common Ancestor Commit: Where both branches had the same content.
- Latest Revisions: Endpoints of each branch.
- Git creates a new merge commit to connect the branches.

### Rebase

Rebase rewrites commit history to make development appear linear. It removes commits from one branch temporarily, applies new commits from another branch, and then reapplies the removed commits.

Important Rule: Do not rewrite commits that have already been pushed to a shared repository.

Instead use it for cleaning up your local commit hsitory before merging it into a shared team branch.

- git rebase <branch>: Rebase the current branch onto <branch>.
- git will remove all the commits from the current branch
- apply the commits from the <branch>
- apply the removed commits.

## Stash

Stash allows you to save changes temporarily and reapply them later. It's useful when you're not ready to commit changes but need to switch branches.

- `git stash` to save changes.
- `git stash list` to list stashes.
- `git stash pop` to reapply and remove the last stash.
- `git stash apply` to reapply the last stash.
- `git stash save <name>` to save a named stash.
- `git stash apply <stash_index>` to reapply a specific stash.
- `git stash drop` to remove the last stash.
- `git stash clear` to remove all stashes.

## Interactive Rebase => (Weak in this section)

- change a commit's message
- delete commits
- reorder commits
- combine multiple commits into one
- edit / split an existing commit intomultiple new ones

1. How far back do you want to go?
2. `git rebase -i HEAD~3` to go back 3 commits. to go back to the first commit use `git rebase -i --root`.
3. `pick` to keep the commit as is.
4. `reword` to change the commit message.
5. `squash` to combine the commit with the previous commit.

## Cherry-Pick

Suppose you accidentally committed on the master branch instead of the feature/newsletter branch.

- `git checkout feature/newsletter` to switch to the feature/newsletter branch.
- `git cherry-pick <commit-hash>` to copy the commit from the master branch to the feature/newsletter branch.
- Clean Up the Master Branch (Optional):
  - `git checkout master` to switch to the master branch.
  - `git reset --hard HEAD~1` to remove the last commit from the master branch.

## Reflog

The reflog is Git's diary, logging every movement of the HEAD pointer. It's invaluable for undoing mistakes.

1. `git reset --hard <commit-hash>` to go back to a previous commit. or `git reset --hard HEAD~1` to go back one commit.
2. `git reflog` to see the history of the HEAD pointer.
3. `git reset <commit-hash>` to go back to a previous commit.

> `git checkout -b <branch-name> <commit-hash>` to create a new branch from a previous commit.

also if you remove branch by mistake you can recover it by using `git reflog` and see when you checkout to another branch and then you can recover it by `git checkout -b <branch-name> <commit-hash>`.

## Revert

Revert is a safe way to undo changes. It creates a new commit that undoes the changes from a previous commit.

- `git revert <commit-hash>` to undo the changes from a previous commit.
- `git revert HEAD` to undo the last commit.
- `git revert HEAD~2` to undo the last 2 commits.

## Submodules

Submodules allow you to keep a Git repository as a subdirectory of another Git repository. They are useful for including third-party libraries without mixing external code with your project files.

- Before this approach: you have to copy the code from the third-party library and paste it into your project. (ugly approach)

- `git submodule add <repository-url>` to add a submodule to your project.

## Search and Find

You can filter your commit history by various criteria:

- By Date `git log --after="2023-07-01" --before="2023-07-05"`
- By Commit Message `git log --grep="refactored"`
- By Author `git log --author="Heinemeier"`
- By File `git log -- README.md`
- By Branch Differences `git log feature/login..main` (commits in main that are not in feature/login)
