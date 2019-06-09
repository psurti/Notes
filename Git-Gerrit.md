https://www.bennadel.com/blog/3587-my-opinionated-git-cheat-sheet.htm

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

#### Log history

{various entries}
````
git log --pretty=oneline --max-count=2
git log --pretty=oneline --since='5 minutes ago'
git log --pretty=oneline --until='5 minutes ago'
git log --pretty=oneline --author=<your name>
git log --pretty=oneline --all
````
{changes made within last week (optional --author=prsurt)}
````
git log --all --pretty=format:"%h %cd %s (%an)" --since='7 days ago'
````
{fancy output}
````
git log --pretty=format:"%h %ad | %s%d [%an]" --graph --date=short
````
#### Alias a git command
````
git config --global alias.st status
````

#### Undo a  commit 
{with original and cancelled commits in history}
````
git revert <HEAD|commit-id>
````
{...discard all changes since then}
````
git reset --hard <tag|commit-id>
````
{...preserve all changes as unstaged changes}
````
git reset <commit-id>
````
{....preserve uncommitted local changes}
````
git reset --keep <commit-id>
````
#### Amend an existing commit
````
git commit -m "fix last existing commit"
````

#### Rebase vs Merge
Don’t use the rebase command …
1. If the branch is public and shared. Rewriting such branches will hinder the work of other team members.
2. When the exact commit branch history is important (because the rebase command rewrites the history of commits).
Given the above recommendations, I prefer to use rebase for short-term, local branches and the merge command for branches in the public repository.

#### Overwite local with the remote repo
````
git fetch origin master
git reset --hard FETCH_HEAD
git clean -di
````
{another variation}
````
 git fetch
 git reset --hard origin/your-branch-name
 ````
#### Discard local changes in a file
````
git checkout HEAD <file>
````
````
