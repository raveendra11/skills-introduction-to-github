## Git Commands

| Command | Description |
|---------|-------------|
| `git status` | Displays the current branch, modified files, staged files, and untracked files. |

**Syntax:**
```bash
git status
```

---

| Command | Description |
|---------|-------------|
| `git add` | Adds new or modified files to the staging area before committing. |

**Syntax:**
```bash
git add filename.txt
git add .
```

---

| Command | Description |
|---------|-------------|
| `git restore` | Restores files by discarding uncommitted changes, unstaging files, recovering deleted files, or restoring files from another commit or branch. |

**Syntax:**
```bash
# Discard all uncommitted changes
git restore .

# Unstage a file
git restore --staged filename.txt

# Discard changes in a specific file
git restore filename.txt

# Restore a file from a specific commit or branch
git restore --source=<commit_hash_or_branch> filename.txt
```

---

| Command | Description |
|---------|-------------|
| `git commit` | To saves changes locally on your own machine. |

**Syntax:**
```bash
git commit
git commit -m "here is your message."

```

---

| Command | Description |
|---------|-------------|
| `git branch` | To see which branch currenlty you are in. |

**Syntax:**
```bash
git branch

```
---

| Command | Description |
|---------|-------------|
| `git log` | Displays the commit history of the current branch, showing commit IDs, authors, dates, and commit messages. |

**Syntax:**
```bash
# Show complete commit history
git log

# Show each commit in a single line
git log --oneline

# Show the last 5 commits
git log -5

# Show commit history with a graph
git log --oneline --graph --all
```
---

| Command | Description |
|---------|-------------|
| `git stash` | Temporarily saves your uncommitted changes without committing them, allowing you to switch branches or work on something else. |

**Syntax:**
```bash
# Stash all tracked changes
git stash

# Stash changes with a message
git stash push -m "Work in progress"

# List all stashes
git stash list

# Apply the latest stash (keep it in the stash list)
git stash apply

# Apply and remove the latest stash
git stash pop

# Remove the latest stash
git stash drop

# Clear all stashes
git stash clear
```
---

| Command | Description |
|---------|-------------|
| `git diff` | Shows the differences between files in your working directory, staging area, commits, or branches. Useful for reviewing changes before committing. |

**Syntax:**
```bash
# Show unstaged changes
git diff

# Show staged changes
git diff --staged

# Compare two commits
git diff <commit1> <commit2>

# Compare two branches
git diff <branch1> <branch2>

# Show changes for a specific file
git diff <file>
```

| Command | Description |
|---------|-------------|
| `git checkout` | Switches between branches or restores files from a specific commit or branch. It can also be used to create and switch to a new branch. *(Note: For newer Git versions, `git switch` and `git restore` are recommended for these tasks.)* |

**Syntax:**
```bash
# Switch to an existing branch
git checkout <branch-name>

# Create and switch to a new branch
git checkout -b <new-branch>

# Restore a specific file from the latest commit
git checkout -- <file>

# Restore a file from a specific commit
git checkout <commit> -- <file>

# Switch to a specific commit (detached HEAD)
git checkout <commit>
```
---

| Command | Description |
|---------|-------------|
| `git revert` | Reverts the changes introduced by a specific commit by creating a new commit. Unlike `git reset`, it does not remove commit history, making it safe for shared repositories. |

**Syntax:**
```bash
# Revert a specific commit
git revert <commit-hash>

# Revert the latest commit
git revert HEAD

# Revert multiple commits
git revert <oldest-commit>^..<latest-commit>

# Revert a commit without editing the commit message
git revert --no-edit <commit-hash>
```
---
| Command | Description |
|---------|-------------|
| `git cherry-pick` | Applies the changes from a specific commit onto your current branch without merging the entire branch. It is useful for selectively applying commits. |

**Syntax:**
```bash
# Apply a specific commit to the current branch
git cherry-pick <commit-hash>

# Apply multiple commits
git cherry-pick <commit1> <commit2>

# Apply a range of commits
git cherry-pick <start-commit>^..<end-commit>

# Continue after resolving conflicts
git cherry-pick --continue

# Abort the cherry-pick operation
git cherry-pick --abort
```
---
| Command | Description |
|---------|-------------|
| `git reflog` | Shows a log of where your `HEAD` and branch references have been. It is useful for recovering lost commits, undoing accidental resets, or finding commits that are no longer referenced by a branch. |

**Syntax:**
```bash
# Show the reflog
git reflog

# View the reflog for a specific branch
git reflog <branch-name>

# Recover a previous state using a reflog entry
git reset --hard HEAD@{2}

# Create a new branch from a previous reflog entry
git checkout -b recovered-branch HEAD@{3}
```
---

| Command | Description |
|---------|-------------|
| `git reset` | Moves the current branch to a previous commit. It can also unstage files or discard commits and changes depending on the option used. **Use `--hard` with caution**, as it permanently removes uncommitted changes. |

**Syntax:**
```bash
# Unstage a specific file
git reset <file>

# Unstage all staged files
git reset

# Undo the last commit (keep changes staged)
git reset --soft HEAD~1

# Undo the last commit (keep changes unstaged)
git reset --mixed HEAD~1

# Undo the last commit and discard all changes
git reset --hard HEAD~1

# Reset to a specific commit
git reset --hard <commit-hash>
```
---

| Command | Description |
|---------|-------------|
| `git merge` | Combines changes from one branch into the current branch. It is commonly used to integrate feature branches into the main branch. |

**Syntax:**
```bash
# Merge a branch into the current branch
git merge <branch-name>

# Merge with a custom commit message
git merge <branch-name> -m "Merge feature branch"

# Abort a merge if conflicts occur
git merge --abort

# Perform a fast-forward merge (when possible)
git merge --ff <branch-name>

# Create a merge commit even if a fast-forward is possible
git merge --no-ff <branch-name>
```

---

| Command | Description |
|---------|-------------|
| `git fetch` | Downloads the latest commits, branches, and tags from a remote repository without merging them into your current branch. It allows you to review changes before integrating them. |

**Syntax:**
```bash
# Fetch changes from the default remote (origin)
git fetch

# Fetch changes from a specific remote
git fetch <remote-name>

# Fetch a specific branch
git fetch <remote-name> <branch-name>

# Fetch all remotes
git fetch --all

# Fetch all branches and remove deleted remote-tracking branches
git fetch --all --prune
```
---

| Command | Description |
|---------|-------------|
| `git pull` | Fetches the latest changes from a remote repository and merges them into the current branch. It is equivalent to running `git fetch` followed by `git merge`. |

**Syntax:**
```bash
# Pull changes from the default remote (origin)
git pull

# Pull changes from a specific remote and branch
git pull <remote-name> <branch-name>

# Pull using rebase instead of merge
git pull --rebase

# Pull all updates from the remote
git pull --all

# Pull and automatically create a tracking branch
git pull --set-upstream <remote-name> <branch-name>
```

---

| Command | Description |
|---------|-------------|
| `git remote` | Manages remote repositories. It allows you to view, add, rename, remove, and update remote repository connections such as `origin`. |

**Syntax:**
```bash
# List all remote repositories
git remote -v

# Add a new remote repository
git remote add <remote-name> <repository-url>

# Rename a remote
git remote rename <old-name> <new-name>

# Remove a remote
git remote remove <remote-name>

# Show information about a remote
git remote show <remote-name>

# Change the URL of an existing remote
git remote set-url <remote-name> <new-repository-url>
```
---

| Command | Description |
|---------|-------------|
| `git stash` | Saves uncommitted changes (staged and unstaged) to a stack and reverts the working directory to match HEAD. It is equivalent to running `git stash push`. |

**Syntax:**
```bash
# Stash current changes with default message
git stash

# Stash with a descriptive message
git stash push -m "description"

# Stash including untracked files
git stash push -u

# Stash only staged changes
git stash push --staged

# List all saved stashes
git stash list

# Apply the most recent stash and keep it on the stack
git stash apply [stash@{n}]

# Apply the most recent stash and remove it from the stack
git stash pop [stash@{n}]

# Show diff of a specific stash
git stash show -p [stash@{n}]

# Create a new branch from a stash
git stash branch <branch-name> [stash@{n}]

# Delete a specific stash
git stash drop stash@{n}

# Delete all stashes
git stash clear
```
---

| Command | Description |
|---------|-------------|
| `git tag` | Creates, lists, and manages tags used to mark specific points in Git history, such as software releases or important versions. |

**Syntax:**

```bash
# List all tags
git tag

# Create a lightweight tag
git tag v1.0.0

# Create an annotated tag
git tag -a v1.0.0 -m "Version 1.0.0"

# Show information about a tag
git show v1.0.0

# Delete a local tag
git tag -d v1.0.0

# Push a specific tag to the remote repository
git push origin v1.0.0

# Push all tags to the remote repository
git push origin --tags

# Delete a remote tag
git push origin --delete v1.0.0
```
---

| Command | Description |
|---------|-------------|
| `git clone` | Creates a local copy of a remote Git repository. |

**Syntax:**
```bash
# Clone a repository
git clone <repository-url>

# Clone a repository into a specific directory
git clone <repository-url> <directory-name>

# Clone a specific branch
git clone -b <branch-name> <repository-url>

---

| Command | Description |
|---------|-------------|
| `git push` | Uploads local commits to a remote repository, allowing others to access the latest changes. |

**Syntax:**
```bash
# Push the current branch to the remote repository
git push

# Push a specific branch to the remote repository
git push <remote-name> <branch-name>

# Push and set the upstream branch
git push -u <remote-name> <branch-name>

# Push all local branches
git push --all

# Push all tags
git push --tags

# Delete a remote branch
git push <remote-name> --delete <branch-name>
```
---

| Command | Description |
|---------|-------------|
| `git rebase` | Reapplies commits from one branch on top of another branch, creating a cleaner and more linear Git history. |

**Syntax:**
```bash
# Rebase the current branch onto another branch
git rebase <branch-name>

# Rebase onto the latest main branch
git rebase main

# Continue a rebase after resolving conflicts
git rebase --continue

# Abort the rebase
git rebase --abort

# Skip the current commit during a rebase
git rebase --skip

# Start an interactive rebase for the last 3 commits
git rebase -i HEAD~3

---

| Command | Description |
|---------|-------------|
| `git bisect` | Uses binary search to find the commit that introduced a bug by testing different commits between a known good and bad state. |

**Syntax:**
```bash
# Start a bisect session
git bisect start

# Mark the current commit as bad
git bisect bad

# Mark a known good commit
git bisect good <commit-hash>

# After testing, mark the current commit
git bisect good
git bisect bad

# End the bisect session
git bisect reset
```
---
| Command | Description |
|---------|-------------|
| `git show` | Displays detailed information about a specific commit, including its commit message, author, date, and changes made. |

**Syntax:**
```bash
# Show the latest commit
git show

# Show a specific commit
git show <commit-hash>

# Show only the commit statistics
git show --stat <commit-hash>

# Show changes for a specific file in a commit
git show <commit-hash> -- <filename>

# Show the latest commit in one line
git show --oneline HEAD
```
---
| Command | Description |
|---------|-------------|
| `git clean` | Removes untracked files and directories from the working directory. |

**Syntax:**
```bash
# Show untracked files that would be removed
git clean -n

# Remove untracked files
git clean -f

# Remove untracked files and directories
git clean -fd

# Remove untracked and ignored files
git clean -fdx
```
---
| Command | Description |
|---------|-------------|
| `git blame` | Shows who last modified each line of a file, along with the commit information and author details. |

**Syntax:**
```bash
# Show who last modified each line of a file
git blame <filename>

# Show line numbers
git blame -n <filename>

# Ignore whitespace changes
git blame -w <filename>

# Show information for a specific range of lines
git blame -L 10,20 <filename>
```
---
| Command | Description |
|---------|-------------|
| `git config` | Configures Git settings, such as your username, email address, editor, and other preferences. |

**Syntax:**
```bash
# View all Git configuration settings
git config --list

# Set your global username
git config --global user.name "Your Name"

# Set your global email address
git config --global user.email "your.email@example.com"

# View a specific configuration value
git config user.name

# Set the default text editor
git config --global core.editor "code"
```
---
| Command | Description |
|---------|-------------|
| `git switch` | Switches between branches or creates and switches to a new branch. |

**Syntax:**
```bash
# Switch to an existing branch
git switch <branch-name>

# Create and switch to a new branch
git switch -c <new-branch-name>

# Switch back to the previous branch
git switch -
```
