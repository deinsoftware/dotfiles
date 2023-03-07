# CHEATSHEET GIT

## Basics

|Alias|Command|Description|
|---|---|---|
|`g init`|`git init`|Initialize a local Git repository|
|`g clone <repo> [<path>]`|`git clone <repo> [<path>]`|Create a local copy of a remote repository|

## Snappshoting

|Alias|Command|Description|
|---|---|---|
|`gst`|`git status`|Check status|
|`gaa`|`git add --all`|Add all new and changed files to the staging area|
|`grh`|`git reset`|Removes all files from staging area|
|`guc`|`git reset --hard HEAD`|Undo changes and preserve untracked files|
|`gca`|`git clean -f -d -x`|Clean ALL changes and remove untracked files|
|`ga <file>`|`git add <file>`|Add a file to the staging area|
|`gru <file>`|`git reset -- <file>`|Remove a file from staging area|
|`gcmsg "<message>"`|`git commit -m "<message>"`|Commit changes with message description|
|`gce`|`git commit -a -m "<message>"`|Add all new files and commit changes with message description.|

## Stash

|Alias|Command|Description|
|---|---|---|
|`gsta -m <name>`|`git stash push -m <name>`|Create stash with name|
|`gstall -m <name>`|`git stash --all -m <name>`|Create stash with all files, including untracked and ignored files with name|
|`gstl`|`git stash list`|List down all your stashes|
|`gstaa stash@{n}`|`git stash apply stash@{n}`|To apply a stash and keep it in the stash stack|
|`gstp stash@{n}`|`git stash pop stash@{n}`|To apply a stash and remove it from the stash stack|
|`gstd`|`git stash drop`|Remove a single stash entry from the list of stash entries|
|`gstc`|`git stash clear`|Remove all stashed entries|

## Branching

|Alias|Command|Description|
|---|---|---|
|`gb`|`git branch`|List branches (the asterisk denotes the current branch)|
|`gba`|`git branch -a`|List all branches (local and remote)|
|`gb <branch-name>`|`git branch <branch-name>`|Create new branch|
|`gbd <branch-name>`|`git branch -d <branch-name>`|Delete a branch|
|`gcb <branch-name>`|`git checkout -b <branch-name>`|Create a new branch and switch to it|
|`gco <branch-name>`|`git checkout <branch-name>`|Switch to a branch|
|`gcd`|`git checkout dev`|Switch to dev branch|
|`gco -`|`git checkout -`|Switch to previous branch|

## Remote

|Alias|Command|Description|
|---|---|---|
|`gra origin <path>`|`git remote add origin <path>`|Add a remote repository|
|`grset origin <path>`|`git remote set-url origin <path>`|Set remote repository|
|`gf`|`git fetch`|Gets status of 'origin'. Does not change your working directory or local repository|
|`gf <repo> <branch-name>`|`git fetch <repo> <branch-name>`|Get status of remote <repo> on <branch>|
|`gfa`|`git fetch --all --prune`|Fetch all remote branches, delete branch if upstream is gone|
|`gl`|`git pull`|Incorporates changes from 'origin' into local repo|
|`gl <repo> <branch-name>`|`git pull <repo> <branch-name>`|Incorporates changes from remote <repo> on <branch> into local repo|
|`glod`|`git pull origin dev`|Incorporates changes from remote origin dev into local repo|
|`gp`|`git push`|Incorporates changes from local repo into 'origin'|
|`gpnv`|`git push --no-verify`|Incorporates changes from local repo into 'origin skipping commit hooks'|
|`gpsup`|`git push --set-upstream origin <currentbranch>`|Set upstream current branch|
|`gp <repo> <branch-name>`|`git push <repo> <branch>`|Incorporates changes from local repo into remote <repo> on <branch-name>|
|`gp -d <remote> <branch>`|`git push -d <remote> <branch>`|Delete remote branch|

## Merging

|Alias|Command|Description|
|---|---|---|
|`gd <source-branch> <target-branch>`|`git diff <source-branch> <target-branch>`|Preview changes before merging|
|`gm <branch-name>`|`git merge <branch-name>`|Merge a branch into the active branch|
|`gm <source-branch> <target-branch>`|`git merge  <source-branch> <target-branch>`|Merge a branch into a target branch|
|`gma`|`git merge --abort`|Cancel the whole merge process|
|`glog`|`git log --oneline --decorate --graph`|View changes|

## Oh Shit

|Alias|Command|Description|
|---|---|---|
|`gc!`|`git commit -v --amend`|I need to change the message on my last commit|
|`gcn!`|`git commit -v --no-edit --amend`|I committed and immediately realized I need to make one small change.|

⚠ You should **never** amend commits that have been pushed up to a **public/shared** branch!. Amend commits that only exists in your local copy or you're gonna have a bad time.

## Config

|Alias|Command|Description|
|---|---|---|
|`gcum`|`git config user.name <git_user>`|Set git config user and email|
| |`git config user.email <git_mail>`| |
|`gcu`|`git config credential.username <git_user>`|Set git credentials|
|`ghcum`|`git config user.name <github_user>`|Set GitHub config user and email|
| |`git config user.email <github_mail>`| |
|`ghcu`|`git config credential.username <github_user>`|Set GitHub credentials|
|`gcg`|`git config --edit --global`|Edit git global configurations|
|`gcl`|`git config --edit --local`|Edit git local configurations|
