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
