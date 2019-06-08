#### Resolving merge conflicts with gerrit
```
git checkout master
git pull origin master
git checkout -b <review-numner>-<patchset>
git pull <url> <ref> (Gerrit UI->download menu->copy 'pull' command)
git rebase master
<<fix all conflicts>
git add <file>
git status
git rebase --continue
git push origin HEAD:refs/for/master
```
https://www.entropywins.wtf/blog/2013/07/01/resolving-a-merge-conflict-on-gerrit/
https://osm.etsi.org/wikipub/index.php/Resolving_merge_conflicts
