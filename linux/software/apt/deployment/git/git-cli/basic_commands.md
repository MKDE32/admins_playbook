## Setup & Config
```
git config --global user.name "Name"
git config --global user.email "[mail@example.com](mailto:mail@example.com)"
git config --global core.autocrlf input
git config --global init.defaultBranch main
git config --list
```

## Repository starten / holen
```
git init
git clone <url>
git clone -b <branch> <url>
```

## Status & Überblick
```
git status
git log
git log --oneline --graph --all
git diff
git diff --staged
```

## Änderungen verwalten
```
git add file.txt
git add .
git commit -m "message"
git commit -am "message"
```

## Branching
```
git checkout -b feature-x
git checkout main
git branch
git branch -d feature-x
```

## Merging & Rebase
```
git merge feature-x
git rebase main
git add .
git rebase --continue
```

## Remote
```
git remote add origin <url>
git push origin main
git pull
git fetch
git remote -v
```

## Undo / Fixes
```
git reset --soft HEAD~1
git reset --hard HEAD~1
git checkout -- file.txt
git commit --amend
```

## Pentest / Admin Tricks
```
git add -A
git status
git blame file.txt
git log --all --full-history -- <file>
git log -p | grep password
```

## Stash
```
git stash
git stash pop
git stash list
```

## Cleanup
```
git clean -fd
git clean -fdx
```

## Shortcuts (Aliases)
```
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.cm commit
git config --global alias.st status
```

## Typischer Workflow
```
git clone <repo>
git checkout -b feature
git add .
git commit -m "feat: xyz"
git push origin feature
```

## Regeln

# kein force push auf shared branches
# keine secrets committen
# kleine commits machen
# mit branches arbeiten
