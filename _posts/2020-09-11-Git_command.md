---
layout:     post
title:      Common Git Command
subtitle:   Linux Command
date:       2020-09-11
author:     Tina
#header-img: img/post-bg-ios9-web.jpg
catalog: true
tags:
    - Linux
    - Git
---
# Guideline for code contribution to Git repo:
1. create a branch for specific issue.
    * git checkout -b \<branch name\>
2. modify/add code to repo, and test
3. push the commit to remote branch:
    * git add .
    * git commit -m "XXX"
    * git push origin \<Origin Branch Name\>
4. Make pull request from remote branch to upstream

# squash code before merging
>For example: if there are 3 commits:
1. git rebase -i HEAD~3
(jump into a doc and set the other commit to s/squash except for the last commit)
2. git push origin <branch name> --force

# update forked repo from the upstream repo (rebase upstream):
0. link the remote upstream repo: (needed only the 1st time)
    * check current remote/upstream info: git remote -v 
    * add upstream: git remote add upstream git@github.com:xxx/xxx.git
    * change upstream: git remote set-url upstream git@github.com:xxx/xxx.git
1. git fetch upstream
2. git rebase upstream/master
6. Solve conflicts
<<<===>>>shows conflicts, manually fix them and then git rebase --continue.
7. git push origin <branchname> -force

# Other commands:
* git log: check commits history
* git reflog: show action history
* git reset --hard <commit ID>: hard rollback to specific commit
* git status: check status
* git branch: check branch
* git checkout <branch name>: switch to another branch
* git diff: see the change made to the files from the last commit
* git show <commit_id>: show the git diff of the specific commit
* git apply xxx.diff: apply a diff file to current branch

# How to apply specify code change to a branch:
* If there is no commit:
1. git diff > xxx.diff : to save the diff to a .diff file
2. In the branch you wanna apply the code change, git apply xxx.diff
* If there exists a commit you wanna to apply to one branch from other branch
1. git cherry-pick <commit_id>
* If there are several commits you wanna apply to a branch from other branch
1. git rebase <Branch_Name_You_Want_To_rebase_from>

* (If there is conflict, should be resolved as in Section 2.)
