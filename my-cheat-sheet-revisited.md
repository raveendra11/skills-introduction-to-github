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
