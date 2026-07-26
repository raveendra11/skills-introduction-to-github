git status      - To see which branch you are on, changes you made on existing files and new files added(as untracked files). 
  cmd :
    git status  

git add         - To add new files/changed files to staging area.  
  cmd :
    git add filename.txt 
    git add .  


git restore     - To discard uncommitted changes in all files/specific file, unstage a file, recover a deleted file, restore a file from a specific commit.
  cmd :
    git restore .
    git restore --staged filename.txt
    git restore filename.txt
    git restore --source=<commit_hash_or_branch> filename.txt

git commit      - To saves changes locally on your own machine.
  cmd :
    git commit
