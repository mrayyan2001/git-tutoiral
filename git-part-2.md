# Git & GitHub - Part 1

## Intro to GitHub

- GitHub especially designed for git repositories.
- another remote repository hosting service is GitLab and Bitbucket.

### Create new repository

- Click on the `+` icon in the top right corner.
- Select `New repository`.
- Enter the repository name.
- Add a description.
- Choose public or private.
- Initialize with a README file or not.
- Click `Create repository`.

### We will have two repositories:
- Local repository: on your computer.
- Remote repository: on GitHub.

### Add a Remote Repository

- Go to the repository on GitHub.
- Click on the `Code` button.
- Copy the URL.
- Add the remote repository to your local repository.
- Use the following command:
```bash
git remote add origin <URL>
```

### List of Remote Repositories

```bash
git remote # List all remote repositories
git remote -v # List all remote repositories with URLs
```
> -v stands for verbose. (more detailed)

### Remove a Remote Repository

```bash
git remote remove <name>
```

## Push and Pull

we have two approaches to sync the local and remote repositories:
- Push: Send changes from local to remote.
- Pull: Get changes from remote to local.

## Git Configuration for GitHub

```bash
git config --global user.name "<name>" # Set username
git config --global user.email "<email>" # Set email
git config --global user.credentials <username> # Set credentials
```

Then you need to authenticate your GitHub account.