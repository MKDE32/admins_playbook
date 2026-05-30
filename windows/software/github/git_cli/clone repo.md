# clone without git
## clone + rename
```
git clone <OLD-REPO-URL> tmp
cp -a tmp/. neuer-name/
rm -rf tmp
cd neuer-name
git init
```

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
