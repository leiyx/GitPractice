# 1 GIT原理



# 2 GIT常用命令汇总

https://www.runoob.com/w3cnote/git-guide.html

以前默认branch是master，现在是main

```
ssh-keygen -t rsa -C "your_email@youremail.com"
ssh -T git@github.com
git config --global user.name "your name"
git config --global user.email "your_email@youremail.com"
git clone 远程仓库ssh的地址 克隆到本机的pathname

```



初始化为本地仓库

> git init



添加远程地址(本地仓库关联远程仓库)

> git remote add origin git@github.com:yourName/yourRepo.git



查看当前分支：

> git branch

查看所有分支，包含远程分支 ：

> git branch -a

新建分支：

> git checkout -b newBranchName

删除本地分支：

> git branch -d LocalBranchName

删除远程分支：

> git push origin :RemoteBranchName 或 git push origin --delete RemoteBranchName





推送本地分支到远程分支(远程分支与本地分支同名)：

> git push origin LocalBranchName:RemoteBranchName

让本地分支与远程分支建立关联：

> git branch --set-upstream-to=origin/RemoteBranchName



> git pull origin RemoteBranchName:LocalBranchName



将BranchName中内容合并到当前分支

> git merge BranchName

## 2.1 Git配置

##  



## 2.2 Git分支



## 2.3 Git推送



## 2.4 Git更新与合并