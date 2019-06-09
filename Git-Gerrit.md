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

#### Configure Eclipse for "Push to Gerrit"
```
select Team > Remote > Configure Push to Upstream
select Add
Configure HEAD to point to refs/for/master
Apply > Dry-Run > Save
See Team > Remote > Push to Gerrit and Fetch from Gerrit actions
```
https://eclipsesource.com/blogs/2014/03/07/how-to-get-the-push-to-gerrit-action-back-with-egit/


#### Private branches and merging to Public branch
```
git checkout master
git merge --squash private_feature_branch
git commit -v
```
https://sandofsky.com/blog/git-workflow.html


#### Branch-off from a previous tagged commit
````
git checkout -b newbranch v1.0
````

#### Controlling 'git log' display entries
````
git log --pretty=oneline --max-count=2
git log --pretty=oneline --since='5 minutes ago'
git log --pretty=oneline --until='5 minutes ago'
git log --pretty=oneline --author=<your name>
git log --pretty=oneline --all
````

#### git log changes made within last week (optional --author=prsurt)
Details are provided in the git-log instruction.
````
git log --all --pretty=format:"%h %cd %s (%an)" --since='7 days ago'
````

#### git log fancy output
````
git log --pretty=format:"%h %ad | %s%d [%an]" --graph --date=short
````
