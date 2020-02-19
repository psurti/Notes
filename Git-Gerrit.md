
https://happygitwithr.com/git-intro.html   
https://www.bennadel.com/blog/3587-my-opinionated-git-cheat-sheet.htm  
https://speakerdeck.com/lemiorhan/10-git-anti-patterns-you-should-be-aware-of   

#### Good Commit Messages
https://chris.beams.io/posts/git-commit/   


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
https://www.internalpointers.com/post/squash-commits-into-one-git  


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
````
- Preserves merge commits on public branches
git fetch origin
git rebase -p origin/master
- Does not preserve merge commits for private branches
git pull -r origin master
````
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
#### List files that have merged conflicts
````
git diff --name-only --diff-filter=U
````

#### Undo tbe last branch
````
git reset --merge ORIG_HEAD
````

#### What has changed between local and remote repository?
````
example:
git fetch --dry-run (lets you know there are new changes to remote repository)
  57ae6c5..46a309e  master     -> origin/master

git diff 57ae6c5..46a309e (lets you know all the files changed!)
 or
git diff --stat 57ae6c5..46a309e
````

#### Branch out a stash diverged
This checks out a new branch based on the commit that you created your stash from, and then pops your stashed changes onto it.
````
git stash branch add-stylesheet stash@{1}
Switched to a new branch 'add-stylesheet'
On branch add-stylesheet
Changes to be committed:
new file: style.css
Changes not staged for commit:
modified: index.html
Dropped refs/stash@{1} (32b3aa1d185dfe6d57b3c3cc3b32cbf3e380cc6a)
````
https://www.atlassian.com/git/tutorials/saving-changes/git-stash


#### Commit Hooks
https://codeinthehole.com/tips/a-useful-template-for-commit-messages/   


#### Remove cached file (after add)
```
Removes all previous adds
git rm -r --cached .
Remove single file that was add(ed)
git rm --cached <file>
```
