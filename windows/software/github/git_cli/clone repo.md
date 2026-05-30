# clone without git
## clone + rename
```
git clone https://github.com/MKDE32/project-cherry-tree.git cherry
cp -a cherry/. new/
rm -rf .git
git log --oneline
cd new
git init
```
- deletes git





## commit all
```
git add -A
git commit -m "Initial commit"
```

## add remote
```
git remote add origin https://github.com/MKDE32/project cherry tree.git
```

## push
```
git branch -M main
git push -f origin main
```
