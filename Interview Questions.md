# Git & GitHub Interview Questions

## Beginner and Intermediate Questions

### **Version Control Basics**

1. **What is version control, and why is it important in software development?**

   - **Answer**: Version control is a system that tracks changes to files over time, allowing developers to collaborate, revert to previous versions, and maintain a history of their work. It's crucial for collaboration, tracking changes, and ensuring code stability.

2. **What are the differences between centralized and distributed version control systems?**

   - **Answer**: Centralized VCS (e.g., SVN) has a single server storing all versions, while distributed VCS (e.g., Git) allows every developer to have a full copy of the repository, enabling offline work and better redundancy.

3. **How would you explain Git to someone who has never used version control before?**
   - **Answer**: Git is like a "time machine" for your code. It lets you save snapshots of your project at different points in time, so you can go back to any previous state if something goes wrong.

---

### **Installing and Basic Configuration of Git**

4. **How do you install Git on your system? (For Windows, macOS, and Linux)**

   - **Answer**:
     - Windows: Download from [git-scm.com](https://git-scm.com/) and run the installer.
     - macOS: Use Homebrew (`brew install git`) or download from the official site.
     - Linux: Use package managers like `sudo apt install git` (Ubuntu) or `sudo yum install git` (CentOS).

5. **What is the purpose of `git config`? Provide examples of configuring user name and email.**

   - **Answer**: `git config` sets configuration options for Git. Examples:
     - `git config --global user.name "John Doe"`
     - `git config --global user.email "johndoe@example.com"`

6. **How do you check the current Git configuration settings?**

   - **Answer**: Use `git config --list`.

7. **Where can you find help for Git commands? Provide an example.**
   - **Answer**: Use `git help <command>` or `git <command> --help`. Example: `git help commit`.

---

### **Git Basic Commands**

8. **Explain the difference between `git add` and `git commit`.**

   - **Answer**: `git add` stages changes for the next commit, while `git commit` saves those staged changes to the repository with a message.

9. **What does `git status` tell you, and when would you use it?**

   - **Answer**: `git status` shows the current state of the working directory and staging area, including untracked, modified, and staged files.

10. **How do you clone a remote repository using Git?**

    - **Answer**: Use `git clone <repository_url>`.

11. **What is the purpose of `git diff`, and how do you use it?**

    - **Answer**: `git diff` shows changes between commits, the working tree, and the index. Example: `git diff` shows unstaged changes.

12. **How do you push changes from your local repository to a remote repository?**

    - **Answer**: Use `git push origin <branch_name>`.

13. **What happens if you run `git init` in a directory that already contains a Git repository?**
    - **Answer**: Git initializes a new repository, but it won’t overwrite existing `.git` files unless forced.

---

### **Branching**

14. **What is a branch in Git, and why is it useful?**

    - **Answer**: A branch is a pointer to a specific commit. It allows developers to work on features or fixes independently without affecting the main codebase.

15. **How do you create a new branch in Git?**

    - **Answer**: Use `git branch <branch_name>`.

16. **How do you switch between branches?**

    - **Answer**: Use `git checkout <branch_name>` or `git switch <branch_name>`.

17. **What is the difference between `git checkout -b <branch_name>` and `git branch <branch_name>`?**

    - **Answer**: `git checkout -b` creates and switches to the branch, while `git branch` only creates the branch.

18. **How do you push a new branch to a remote repository?**
    - **Answer**: Use `git push origin <branch_name>`.

---

### **Merging**

19. **What is a merge conflict, and how do you resolve it?**

    - **Answer**: A merge conflict occurs when Git cannot automatically merge changes. You resolve it by manually editing the conflicting files and marking them as resolved with `git add`.

20. **What is the difference between `git merge` and `git rebase`?**

    - **Answer**: `git merge` combines branches with a merge commit, preserving history. `git rebase` moves commits onto another branch, creating a linear history.

21. **How do you merge one branch into another?**

    - **Answer**: Use `git merge <branch_name>`.

22. **What happens during a fast-forward merge?**
    - **Answer**: If the target branch has no new commits, Git moves the branch pointer forward without creating a merge commit.

---

### **Git Log**

23. **How do you view the commit history in Git?**

    - **Answer**: Use `git log`.

24. **What does `git log --pretty=oneline` do?**

    - **Answer**: Displays each commit on a single line.

25. **How can you visualize the commit history as a graph?**

    - **Answer**: Use `git log --graph`.

26. **How do you search for commits containing a specific keyword in the commit message?**
    - **Answer**: Use `git log --grep=<keyword>`.

---

### **Move and Remove**

27. **How do you rename or move a file in Git?**

    - **Answer**: Use `git mv <old_path> <new_path>`.

28. **How do you remove a file from the Git repository but keep it in your working directory?**

    - **Answer**: Use `git rm --cached <file>`.

29. **What happens if you delete a file without using `git rm`?**
    - **Answer**: The file remains tracked until you stage the deletion with `git add`.

---

### **Amend**

30. **What is the purpose of `git commit --amend`?**

    - **Answer**: It modifies the most recent commit, such as updating the commit message or adding missed changes.

31. **When should you avoid using `git commit --amend`?**
    - **Answer**: Avoid it after pushing to a shared branch, as it rewrites history.

---

### **Stash**

32. **What is `git stash`, and when would you use it?**

    - **Answer**: `git stash` temporarily saves changes that aren’t ready to be committed, allowing you to switch branches or clean your workspace.

33. **How do you apply stashed changes back to your working directory?**

    - **Answer**: Use `git stash pop` or `git stash apply`.

34. **What is the difference between `git stash pop` and `git stash apply`?**
    - **Answer**: `pop` applies and removes the stash, while `apply` keeps it.

---

### **Gitignore**

35. **What is a `.gitignore` file, and why is it important?**

    - **Answer**: `.gitignore` specifies files or directories to exclude from version control, preventing accidental commits of sensitive or unnecessary files.

36. **How do you ignore specific files or directories in Git?**

    - **Answer**: Add patterns to `.gitignore`. Example: `/logs/` ignores the `logs` directory.

37. **Can you ignore files that have already been committed to the repository? If yes, how?**
    - **Answer**: Yes, update `.gitignore` and use `git rm --cached <file>`.

---

### **Gitflow**

38. **What is Gitflow, and how does it help in managing releases?**

    - **Answer**: Gitflow is a branching model that uses feature, release, and hotfix branches to manage development and releases systematically.

39. **Describe the different types of branches used in Gitflow.**

    - **Answer**: `main` (production), `develop` (integration), `feature` (new features), `release` (preparing for production), `hotfix` (urgent fixes).

40. **How do you start a new feature branch in Gitflow?**
    - **Answer**: Use `git flow feature start <feature_name>`.

---

### **Rebase**

41. **What is `git rebase`, and how does it differ from `git merge`?**

    - **Answer**: `rebase` moves commits onto another branch, while `merge` combines branches with a merge commit.

42. **What are the risks of rebasing, and when should you avoid it?**

    - **Answer**: Rebase rewrites history, which can cause issues on shared branches. Avoid it on public branches.

43. **How do you perform an interactive rebase?**
    - **Answer**: Use `git rebase -i <base>`.

---

### **Tags**

44. **What are Git tags, and why are they useful?**

    - **Answer**: Tags mark specific points in history, often used for releases.

45. **How do you create a lightweight tag and an annotated tag?**

    - **Answer**:
      - Lightweight: `git tag <tag_name>`
      - Annotated: `git tag -a <tag_name> -m "message"`

46. **How do you list all tags in a repository?**

    - **Answer**: Use `git tag`.

47. **How do you delete a tag locally and remotely?**
    - **Answer**:
      - Locally: `git tag -d <tag_name>`
      - Remotely: `git push origin --delete <tag_name>`

---

### **Searching**

48. **How do you search for a specific string in your codebase using Git?**

    - **Answer**: Use `git grep <string>`.

49. **What is the difference between `git grep` and `git log -S`?**

    - **Answer**: `git grep` searches the working directory, while `git log -S` searches commit diffs.

50. **How do you count occurrences of a search string in your repository?**
    - **Answer**: Use `git grep --count <string>`.

---

### **Reset**

51. **What are the three types of `git reset` (`soft`, `mixed`, `hard`), and what do they do?**

    - **Answer**:
      - `soft`: Moves HEAD but keeps changes staged.
      - `mixed`: Moves HEAD and unstages changes.
      - `hard`: Moves HEAD and discards changes.

52. **When should you use `git reset --hard`?**

    - **Answer**: Only when you’re sure you want to discard changes permanently.

53. **What is the difference between `git reset` and `git revert`?**
    - **Answer**: `reset` rewrites history, while `revert` creates a new commit to undo changes.

---

### **Configs**

54. **What are Git configurations, and how do they work?**

    - **Answer**: Configurations customize Git behavior. They are stored in `.gitconfig` files.

55. **How do you set a global Git configuration?**

    - **Answer**: Use `git config --global`.

56. **What is the difference between `--local`, `--global`, and `--system` configurations?**
    - **Answer**:
      - `local`: Repository-specific.
      - `global`: User-specific.
      - `system`: System-wide.

---

### **Hooks**

57. **What are Git hooks, and where are they stored?**

    - **Answer**: Hooks are scripts triggered by Git events, stored in `.git/hooks`.

58. **Name some common client-side Git hooks and their purposes.**

    - **Answer**: `pre-commit`, `post-commit`, `pre-push`.

59. **How do you configure a pre-commit hook to run tests before committing?**
    - **Answer**: Write a script in `.git/hooks/pre-commit` that runs tests.

---

### **Submodules**

60. **What are Git submodules, and when would you use them?**

    - **Answer**: Submodules allow embedding one repository inside another, useful for dependencies.

61. **How do you add a submodule to a repository?**

    - **Answer**: Use `git submodule add <repo_url>`.

62. **How do you update a submodule to the latest commit?**
    - **Answer**: Use `git submodule update --remote`.

---

### **Blame**

63. **What is `git blame`, and how is it useful?**

    - **Answer**: `git blame` shows who last modified each line of a file, useful for debugging.

64. **How do you use `git blame` to find out who last modified a specific line of code?**
    - **Answer**: Use `git blame <file>`.

---

### **Projects & Organization**

65. **How do you create a new repository on GitHub/GitLab?**

    - **Answer**: Click "New Repository," fill in details, and initialize it.

66. **What is the difference between a public and private repository?**

    - **Answer**: Public repositories are visible to everyone, while private repositories restrict access.

67. **How do you manage collaborators and permissions in a Git hosting platform like GitHub?**

    - **Answer**: Use the "Settings > Collaborators" section to add users and assign roles.

68. **What are GitHub Actions, and how can they be used to automate workflows?**
    - **Answer**: GitHub Actions automate tasks like CI/CD pipelines using YAML configuration files.

## Expert Questions

### **Git Internals**

1. **What is Git's content-addressable file system?**

   - **Answer**: Git stores objects (commits, trees, blobs) in a `.git/objects` directory using their SHA-1 hash as the filename. This ensures immutability and deduplication.

2. **What are the three types of Git objects, and what do they represent?**

   - **Answer**:
     - **Blob**: Represents file content.
     - **Tree**: Represents a directory structure (files and subdirectories).
     - **Commit**: Represents a snapshot of the repository at a point in time, including metadata like author, message, and parent commit(s).

3. **How does Git store and retrieve objects?**

   - **Answer**: Objects are stored as compressed files in `.git/objects` using their SHA-1 hash. Retrieval happens via the hash or plumbing commands like `git cat-file`.

4. **What is the purpose of `git cat-file`?**

   - **Answer**: It examines the content, type, and size of objects in the Git object database. Example: `git cat-file -p <hash>`.

5. **What are Git refs, and how do they work?**

   - **Answer**: Refs are pointers to commits (e.g., branches, tags). They are stored in `.git/refs` and allow humans to reference commits without using hashes.

6. **What are pack files, and why are they used?**
   - **Answer**: Pack files compress multiple objects into a single file for efficiency. They reduce storage space and improve performance during cloning and fetching.

---

### **Plumbing Commands**

7. **What are Git plumbing commands, and how do they differ from porcelain commands?**

   - **Answer**: Plumbing commands are low-level commands that directly interact with Git's internal data structures (e.g., `git hash-object`, `git cat-file`). Porcelain commands are high-level, user-friendly commands (e.g., `git add`, `git commit`).

8. **How would you create a blob object manually using plumbing commands?**

   - **Answer**: Use `git hash-object -w <file>` to create a blob object and store it in the object database.

9. **How do you view the raw contents of a commit object?**

   - **Answer**: Use `git cat-file -p <commit-hash>`.

10. **What is the difference between `git write-tree` and `git commit-tree`?**
    - **Answer**:
      - `git write-tree`: Creates a tree object from the current index.
      - `git commit-tree`: Creates a commit object from a tree object.

---

### **Rebase Interactive**

11. **How do you use `git rebase -i` to remove commits?**

    - **Answer**: Run `git rebase -i HEAD~4`, then delete the lines corresponding to the commits you want to remove.

12. **How do you squash commits using interactive rebase?**

    - **Answer**: In the interactive rebase editor, replace `pick` with `squash` (or `s`) for the commits you want to combine.

13. **How can you edit commit messages during an interactive rebase?**

    - **Answer**: Replace `pick` with `edit` (or `e`) for the commit you want to modify, then amend the commit message using `git commit --amend`.

14. **How do you split a commit during an interactive rebase?**

    - **Answer**: Mark the commit with `edit`, reset it (`git reset HEAD^`), stage changes selectively, and create new commits.

15. **How do you reorder commits using interactive rebase?**
    - **Answer**: Rearrange the lines in the interactive rebase editor to change the order of commits.

---

### **Git Administration**

16. **What is `git filter-branch`, and when would you use it?**

    - **Answer**: `git filter-branch` rewrites history by applying filters to a range of commits. It’s used for tasks like removing sensitive data or restructuring history.

17. **What does `git fsck` do?**

    - **Answer**: `git fsck` checks the integrity of the Git repository by verifying objects and detecting corruption or dangling references.

18. **What is `git reflog`, and how is it useful?**

    - **Answer**: `git reflog` records all changes to branch tips and HEAD, allowing recovery of lost commits or branches.

19. **What does `git gc` do, and when should you run it?**
    - **Answer**: `git gc` performs garbage collection, such as packing objects and pruning unreachable objects. It’s typically run automatically but can be triggered manually for optimization.

---

### **Debugging**

20. **How does `git bisect` help in finding bugs?**

    - **Answer**: `git bisect` performs a binary search through commits to identify the commit that introduced a bug. You mark commits as "good" or "bad" until the faulty commit is isolated.

21. **How do you automate `git bisect` with a test command?**
    - **Answer**: Use `git bisect run <script>`, where `<script>` is a command or script that returns 0 for "good" and non-zero for "bad."

---

### **Merge Strategies**

22. **What are some common Git merge strategies, and when would you use them?**

    - **Answer**:
      - **resolve**: Resolves conflicts using a simple algorithm.
      - **recursive**: Default strategy for merging two branches.
      - **octopus**: Merges more than two branches simultaneously.
      - **ours**: Ignores changes from other branches, keeping only the current branch’s changes.
      - **subtree**: Handles merges where one project is a subdirectory of another.

23. **How do you specify a custom merge strategy?**
    - **Answer**: Use `-s <strategy>` with `git merge`. Example: `git merge -s ours`.

---

### **Rewriting History**

24. **How do you undo a commit without losing its changes?**

    - **Answer**: Use `git reset --soft HEAD^` to move the branch pointer back while keeping changes staged.

25. **How do you rewrite history using `git reflog`?**

    - **Answer**: Identify the desired commit from `git reflog`, then reset or cherry-pick it.

26. **What are the risks of rewriting history?**
    - **Answer**: Rewriting history changes commit hashes, which can cause issues for collaborators relying on the original history.

---

### **Git Server**

27. **How do you set up a Git server?**

    - **Answer**:
      - SSH: Create a bare repository and share it via SSH.
      - HTTP(S): Use a web server like Apache or Nginx with Git hooks.
      - Git Daemon: Use `git daemon` for lightweight read-only access.

28. **What protocols can Git use to communicate with a remote repository?**
    - **Answer**: SSH, HTTPS, Git protocol, and file-based protocols.

---

### **Git in Apps**

29. **What is Libgit2, and how is it used?**

    - **Answer**: Libgit2 is a portable, pure C implementation of Git core methods. It’s used to embed Git functionality in applications.

30. **What is JGit, and where is it commonly used?**

    - **Answer**: JGit is a Java implementation of Git. It’s commonly used in Eclipse and other Java-based tools.

31. **What is go-git, and what are its advantages?**
    - **Answer**: go-git is a Go implementation of Git. It’s lightweight and integrates well with Go applications.

---

### **Additional Advanced Questions**

32. **How do you recover a deleted branch using `git reflog`?**

    - **Answer**: Find the commit hash of the branch tip from `git reflog`, then recreate the branch using `git checkout -b <branch_name> <hash>`.

33. **What is the difference between `git prune` and `git gc`?**

    - **Answer**: `git prune` removes unreachable objects, while `git gc` performs garbage collection, including packing and pruning.

34. **How do you clean up unused objects in a Git repository?**

    - **Answer**: Use `git gc` or `git prune`.

35. **What is the purpose of `.git/hooks`, and how can you use it?**
    - **Answer**: `.git/hooks` contains scripts that trigger actions during Git events (e.g., pre-commit, post-push). You can customize these scripts for automation.
