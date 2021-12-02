git remote show origin


**Initial push - Fresh repo**

```git init

git add —all

git commit -m”messga”

git push

git remote add origin git@github.com:ziaur25/cucumber-suite

git push -u origin master
```


**If code is already tracked by git**

```
cd existing project

git remote set-url origin git@github.com:username/repo

git push -u origin master
```

