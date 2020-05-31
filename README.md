# git-study
git使用的一些笔记

***git tag操作***

git tag -l 查看本地tag

git ls-remote --tag 查看当前分支远程标签

git tag [tagName] 给当前分支打tag（本地）

git push origin --tag 推送本地所有tag到远端

git push origin [tagName] 推送本地名为[name]的tag到远端

git show [tagName] 查看tag的commit信息


***git 分支操作***

git checkout -b feature/xxx

git checkout [commitID] -b [newBranchName] 基于[commitId]创建本地新分支，名为[newBranchName]

git checkout tag & git checkout branch 前一句是切换到某个tag，当前是一个临时分支，若要切换回之前的分支需要checkout之前的branch
 
git reset HEAD^ 或者get reset HEAD~1 取消最近一个commit 回到待add的状态， 如果加了 --hard 则同时会自动清除未提交的内容

git push origin [branchName] 把创建的新分支提交到远端仓库

git branch --set-upstream-to=origin/[branchName] [branchName1] 把当前分支branchName1关联到远端branchName

git push origin -d [branchName] 删除远端分支

git branch 查看本地分支

git branch -r 查看远端分支

git branch -a 查看本地和远端分支

git remote update origin --prune 保证本地显示的远端分支跟仓库上的一致

git branch -d feature/xxx    -d表示普通删除，如果该分支没有被merge过，会提示是否强行删除，强行删除用-D

git push origin --delete [branchName] 删除远程分支

***git cherry-pick***

git cherry-pick xxxxxx 相当于把别的分支的xxxxxx这次commit在本分支提交一次