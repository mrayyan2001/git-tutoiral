# Git Setup

## Introduction

- Git is a free, open-source distributed version control system used to track changes in source code during software development.
- It helps manage collaboration among teams, allowing users to track who made changes, why, and when.

## Download and Install Git

- Download Git from [git-scm.com](https://git-scm.com/).
- or if you're using windows and have `winget` installed, you can run `winget install Git.Git` in the terminal.

> winget is a package manager for Windows. You can install it from the Microsoft Store.

```bash
git --version # check the version
```

## Configure Git

### Configuration Levels

- Git has three configuration levels:
  - System: Applies to all users on the system. (`--system`)
  - Global: Applies to the current user. (`--global`)
  - Local: Applies to the current repository. (`--local`)

### Basic Configuration

- `git config --global user.name "<Your-Full-Name>"` -> set your name
- `git config --global user.email "<Your-Email>"` -> set your email
- `git config --list` -> list all configurations
- `git config --global core.editor "code --wait"` -> set Visual Studio Code as the default editor
