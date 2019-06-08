#### Resolving merge conflicts with gerrit
```
git pull origin master
git review -d <commit-id>
git rebase master
“fix conflicts”
git add *
git rebase –continue
git review
```
https://www.entropywins.wtf/blog/2013/07/01/resolving-a-merge-conflict-on-gerrit/
