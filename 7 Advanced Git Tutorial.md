# Advanced Git Tutorial

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

![alt text](image-22.png)

Suppose you accidentally committed on the master branch instead of the feature/newsletter branch.

- `git checkout feature/newsletter` to switch to the feature/newsletter branch.
- `git cherry-pick <commit-hash>` to copy the commit from the master branch to the feature/newsletter branch.
- Clean Up the Master Branch (Optional):
  - `git checkout master` to switch to the master branch.
  - `git reset --hard HEAD~1` to remove the last commit from the master branch.

## Reflog
