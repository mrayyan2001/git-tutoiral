# Practice Scenario

## Scenario 1

We have an existing project.

1. `git init` to initialize the repository.
2. `git add .` to add all files to the staging area.
3. `git commit -m "Initial commit"` to commit the changes.
4. Create a repository on GitHub.
5. `git remote add origin <URL>` to add the remote repository.
6. `git push -u origin main` to push the changes to the remote repository.

## Scenario 2

We're starting a new project.

- We want this project to be on GitHub.

### Way 1

1. Create some new code
2. `git init` to initialize the repository.
3. Create a repository on GitHub.
4. Link the local repository to the remote repository.
5. `git push -u origin main` to push the changes to the remote repository.

### Way 2

1. Create a repository on GitHub.
2. `git clone <URL> <folder-name>` to clone the repository to a specific folder.
3. Create some new code.
4. `git add .` to add all files to the staging area.
5. `git commit -m "Initial commit"` to commit the changes.
6. `git push -u origin main` to push the changes to the remote repository.

## Scenario 3

We joined a new team. Their project is already on GitHub.

- Download the team's code.
- Contribute to the code.

Same as Scenario 2, Way 2.

## Scenario 4

Contribute to an open-source project.

1. Fork the repository.
2. Clone the repository to your local machine.
3. Create a new branch.
4. Make changes.
5. `git add .` to add all files to the staging area.
6. `git commit -m "message"` to commit the changes.
7. `git pull origin <branch-name>` to pull the changes from the remote repository. (Avoid conflicts)
8. `git push origin <branch-name>` to push the changes to the remote repository.
9. Create a pull request.
10. Wait for the maintainers to review and merge your changes.
11. Sync your fork with the original repository.
12. Delete the branch.

> Before push the changes, make sure to pull the changes from the remote repository to avoid conflicts.
