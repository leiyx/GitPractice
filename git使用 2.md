# git原理

![git工作流程](../picture/git/git工作流程.png)

![git四区](../picture/git/git四区.png)

工作区，就是我们看到的文件夹目录；

暂存区，就是隐藏的.git目录下的index文件

本地仓库，就是.git文件夹，其中HEAD指向最新放入本地仓库的版本

远程仓库，就是最开始git remote add origin .......  的origin的值；如果使用的github的话，即为github仓库

![git文件的四种状态](../picture/git/git文件的四种状态.png)

# git命令

## 配置信息

git config --global user.name "leiyx"

git config --global user.email 770567756@qq.com

//--global 选项，该命令只需要运行一次，以后git都会使用哪些信息；

git config --list

git remote add origin **.git

git remote rm origin

git config --global core.quotepath false//解决git status等命令，不显示中文的问题

## 查看帮助命令

git help init(command name)

git init(command name) --help

man git-init(command name)

## 查看文件状态

git status

## 初始化仓库

git init

## 工作区与暂存区操作

git add pathname //添加到git的暂存区

git rm -f pathname//从暂存区和工作区删除该文件

当执行 git rm --cached <file> 命令时，会直接从暂存区删除文件，工作区则不做出改变。

git restore --staged a.txt//将文件从暂存区删除，但仍在工作区存在

## 暂存区与本地仓库操作

git commit -m "dsfdsf"//将暂存区和被跟踪的所有文件提交到本地仓库

git commit pathname1 pathname2... -m "dsfa"

git commit -a -m "fdsf"//将暂存区的所有修改都提交到本地仓库（包括删除操作）

git commit --amend//这次提交不作为一次新的提交，将其内容合并到上次提交

### 查看commit的内容

git log -p //查看commit内容

git log

git log --oneline

git log -[length]

git log --skip=2 -3

git log --stat

git show commit-id

*git* *commit* --allow-empty-message -m "" //使用空的*注释提交*

### git rebase?

- [x] git rebase -i hash值 //????????
- [x] git rebase --continue





## 本地仓库与远程仓库操作

git push 远程主机名 本地分支名:远程分支名

git push 远程主机名 本地分支名//默认同名远程分支名，若不存在，则新建

git push 远程主机名  :远程分支名//省略本地分支，表示删除远程分支，与下条命令等价git push origin --delete master

git push origin //本地分支与远程分支存在追踪关系

git push//自动推送到同名远程分支





- [x] ***冲突解决***：git pull 拉去分支下来，手动解决冲突，在git commit 和git push，

git push -fore//强制推送

## 远程仓库到工作区

git pull 远程主机名 远程分支名:本地分支名

与git push类似，只不过最后一项反了过来；

## 分支

git branch   # 查看本地分支

git branch -r  # 查看远程分支

git branch -a  # 查看全部（本地+远程）分支



git checkout –b 分支名  # 创建一个新分支,并切换到该新分支

git branch –d  分支名 # 删除分支

git branch 分支名  # 创建develop分支

git checkout 分支名   # 切换分支



git merge 另一个分支名   # 合并当前分支与另一个分支到当前分支

git rebase 





git branch --set-upstream-to=origin/远程分支名 本地分支名  // 建立本地分支与远程分支的关系

## 撤销回滚

- [x] 

1. 没有commit：暂存区

git clean -f//删除当前目录下所有没有被track过的文件（未添加到暂存区的文件）

git checkout .//以暂存区所有内容覆盖工作区（若工作区有未添加到暂存区的新增文件则还是会存在）

2. commit了但没有push的话：本地仓库中

git reset --hard HEAD~{n}

3. push了：远程仓库中

## git标签

- [x] 

git tag v0.1//标签？？？

​	git tag -a v0.1 -m "lsdjfk"

//操作标签？？？