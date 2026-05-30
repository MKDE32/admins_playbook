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
git remote add origin <NEUE-REPO-URL>
```


