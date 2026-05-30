# clone without git
## clone + rename
```
git clone <OLD-REPO-URL> tmp
cp -a tmp/. new/
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
git remote add origin https://github.com/MKDE32/test2.git
```

## push
```
git branch -M main
git push -f origin main
```
