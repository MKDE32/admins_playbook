
# SETUP
--------------------------------------------

git --version
-> Show installed git version

git config --global user.name "Name"
-> Set global username

git config --global user.email "email@example.com"
-> Set global email

git config --list
-> Show configuration


# START / CLONE
--------------------------------------------

git init
-> Initialize new repository

git clone <url>
-> Clone remote repository

git clone <url> <folder>
-> Clone into specific folder



# STATUS / INSPECT
--------------------------------------------

git status
-> Show modified/staged files

git log
-> Show commit history

git log --oneline
-> Compact commit history

git diff
-> Show unstaged changes

git diff --staged
-> Show staged changes



# ADD / COMMIT
--------------------------------------------

git add <file>
-> Stage file

git add .
-> Stage all changes

git commit -m "message"
-> Commit changes

git commit -am "message"
-> Add + commit tracked files



# BRANCHING
--------------------------------------------

git branch
-> List branches

git branch <name>
-> Create branch

git checkout <branch>
-> Switch branch

git checkout -b <branch>
-> Create + switch branch

git switch <branch>
-> Switch branch (modern)

git switch -c <branch>
-> Create + switch (modern)


--------------------------------------------
# MERGE
--------------------------------------------

git merge <branch>
-> Merge branch into current branch

git rebase <branch>
-> Rebase current branch


--------------------------------------------
# REMOTE (GITHUB / SERVERS)
--------------------------------------------

git remote -v
-> Show remote repositories

git remote add origin <url>
-> Add remote repo

git push
-> Push changes

git push -u origin main
-> Push and set upstream

git pull
-> Fetch + merge changes

git fetch
-> Download changes only


--------------------------------------------
# UNDO / RECOVERY
--------------------------------------------

git restore <file>
-> Undo unstaged changes

git restore --staged <file>
-> Unstage file

git reset --soft HEAD~1
-> Undo last commit, keep changes

git reset --hard HEAD~1
-> Delete last commit (dangerous)

git revert <commit>
-> Safe undo via new commit


--------------------------------------------
# SECURITY / ADMIN NOTES
--------------------------------------------

- git reset --hard destroys local changes
- git push can overwrite remote history if forced
- always check git status before commits
- use branches for safe changes
- sensitive data should never be committed
