# clone without git
```
git clone <OLD-REPO-URL> tmp
rsync -av tmp/ neuer-name/
rm -rf tmp
cd neuer-name
git init
```
