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

### Change the Remote Repository

```bash
git remote set-url origin <URL>
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

or you can add the git URL like this

```bash
git remote add https://<username>@github.com/<...>.git
```

### Personal Access Token

- Go to GitHub.
- Click on your profile.
- Go to `Settings`.
- Click on `Developer settings`.
- Click on `Personal access tokens`.
- Click on `Generate new token`.
- Enter the password.
- Select the scopes.
- Click on `Generate token`.
- Copy the token.
- Use the token as a password.

### Avoid each time entering the username and password

```bash
git config --global credential.helper store # Store the credentials
# or
git config --global credential.helper cache # Cache the credentials for the session
git config --global credential.helper 'cache --timeout=600' # Cache the credentials for 10 minutes
```

## Syncing with Remote Repositories

### Push

- Send changes from local to remote.

```bash
git push origin <branch-name>
```

- you can set upstream to avoid specifying the branch name.

```bash
git push -u origin <branch-name>
```

> -u stands for upstream. (--set-upstream)

- force push: `git push -f origin <branch-name>` even if overwriting the remote repository.

> -f stands for force.

### Download a copy of the remote repository

```bash
git clone <URL> # Clone the repository to the current folder (the repository name will be the folder name)
git clone <URL> <folder-name> # Clone the repository to a specific folder
```

### Pull

- Get changes from remote to local.

```bash
git pull origin <branch-name> # Pull the changes from the remote repository
git pull # Pull the changes from the remote repository if upstream is set
```

- `git pull` = `git fetch` + `git merge` (fetch and merge)

1. `git fetch origin main`
2. `git merge origin/main`

### Fetch

- Get changes from remote to local without merging.

```bash
git fetch origin <branch-name> # Fetch the changes from the remote repository
```

## Summary

### Create Online Backup

1. `git remote add origin <URL>`
2. `git push -u origin <branch-name>`

### Sync Computer => GitHub

1. `git add .`
2. `git commit -m "message"`
3. `git push origin <branch-name> -f`

### Sync GitHub => Computer

1. `git fetch origin <branch-name>`
2. `git pull origin <branch-name>`
