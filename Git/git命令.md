# git -v
查看当前git软件版本

# git config
全局配置文件位置：C:/Users/[用户名]/.git-mm/.gitconfig  
局部配置文件位置：\.git\config  

## 查看配置
```
# 查看所有的全局配置
git config --global --list
# 查看指定仓库配置
git config --local --list
# 查看指定仓库指定配置项
git config user.name
```
## 设置配置
local git config：分别设置提交代码的用户名和电子邮件地址（在.git文件夹内的config文件可查看）  
用法：git config user.name “[name]”  
用法：git config user.email “[email address]”

global git config：设置全局（对整个git软件所有的仓库用全局的名称）  
git config --global user.name [name]  
git config --global user.email [email]

```
// 添加GIT全局配置
git config --global user.name “git” // 配置全局用户名(这个名称将被应用到创建一个ssh连接型远程资源库时)
git config --global user.email coTest_1@163.com // 配置全局邮箱
git config --global gui.encoding utf-8 // 配置GUI编码
git config --global core.quotepath false // 设置不转义中文字符(命令行或bash运行git命令时显示的文件路径不用编码模式显示)
git config --global http.postBuffer 524288000 // 配置Http的Post缓存容量
git config --global i18n.commitencoding utf-8 // 配置提交时的编码
git config --global i18n.logoutputencoding utf-8 // 配置日志输出的编码

git config --global user.name “git”
git config --global user.email coTest_1@163.com
git config --global gui.encoding utf-8
git config --global core.quotepath false
git config --global http.postBuffer 524288000
git config --global i18n.commitencoding utf-8
git config --global i18n.logoutputencoding utf-8

// 删除配置
git config --unset --global user.name
git config --unset --global user.email
git config --unset --global gui.encoding
git config --unset --global core.quotepath
git config --unset --global http.postbuffer
git config --unset --global i18n.commitencoding
git config --unset --global i18n.logoutputencoding

// 查看Git配置信息
git config --global --list
```

## 获取帮助信息
```
# 获取 git config 命令的帮助手册
git help config
# 获取 git config 命令的快速参考
git config -h
```

# git init

在当前路径中创建一个新的代码库，生成.git文件夹  
用法：git init [repository name]

# git clone

通过指定的URL获取一个代码库  
用法：git clone [url]

通过指定的URL获取一个代码库，并取一个本地别名（本地文件夹名称）
git clone [url] [别名]

# git add

将一个文件添加至stage(暂存区)  
用法：git add [file]  

将多个文件（扩展名为...的文件）全部添加至stage(暂存区)  
用法：git add *.扩展名  

将全部变更文件添加至stage(暂存区) 
用法：git add .

# git commit

将暂存区里的内容存入本地仓库中  

在版本历史记录中永久记录文件  
用法：git commit -m “[ Type in the commit message]”  
git commit -m [message]  
git commit -m['message']  
git commit -m["message"]  

将提交git add命令添加的所有文件，并提交git add命令之后更改的所有文件  
用法：git commit -a

# git diff

显示尚未添加到stage的文件的变更  
用法：git diff  

显示添加到stage的文件与当前最新版本之间的差异
用法：git diff –staged  

显示两个分支之间的差异  
用法：git diff [first branch] [second branch]  

# git status

暂存区状态：显示所有需要提交的文件  
用法：git status  
untracked filed：未追踪状态，git未将该文件管理起来

# git rm

删除工作目录中的文件，并将删除动作添加到stage  
用法：git rm [file]  

将文件移出暂存区，放回工作区  
git rm --cached [file]

# git log

显示当前分支的版本历史记录（显示全部版本号，作者，提交时间）  
用法：git log  

一行来显示当前的提交（版本号只显示部分前七位，无作者，无提交时间）  
git log --oneline  

显示某个文件的版本历史记录，包括文件的重命名  
用法：git log –follow[file]  

显示某次提交之前的历史提交记录  
git log [commitID]  
git log [标签名]

# git show

显示指定提交的元数据以及内容变更  
用法：git show [commit]

# git tag

可以给每一个版本增加标签，但标签不能重复  
给指定的提交添加标签（别名），以后就可以通过别名进行访问  
用法：git tag [标签名] [commitID]  

查看所有标签：  
git tag  

删除标签  
git tag -d [标签名]  

标签还可以创建分支，（分支就是引用了一个提交的版本号，而标签就是给版本增加了别名）

# git branch

显示当前代码库中所有的本地分支  
用法：git branch

创建一个分支（git中的分支是基于提交操作的）  
用法：git branch [branch name]

删除指定的分支  
用法：git branch -d [branch name]

## 重命名
1. 本地分支重命名(还没有推送到远程)
```
git branch -m oldName newName
```
2. 远程分支重命名 (已经推送远程-假设本地分支和远程对应分支名称相同)
```
a. 重命名远程分支对应的本地分支
git branch -m oldName newName

b. 删除远程分支
git push --delete origin oldName

c. 上传新命名的本地分支
git push origin newName

d.把修改后的本地分支与远程分支关联
git branch --set-upstream-to origin/newName
```

# git checkout

切换分支  
用法：git checkout [branch name]  

创建一个分支，并切换到新分支上  
用法：git checkout -b [branch name]  

对这个标签所在的提交进行分支创建（标签名即为分支名）  
git checkout -b [标签名]  

# git merge

将指定分支的历史记录合并到当前分支  
用法：git merge [branch name]  

冲突（当前分支|MERGING）：  
<<<<<<< HEAD  
当前分支冲突部分内容  
.=======  
合入指定分支冲突部分内容  
.>>>>>>> [branch name]  

解决冲突：  
人工修改冲突文件为正确内容  
git add [file]
git commit -m 解决冲突

# git remote

可以直接在.git内的config文件修改  
将本地的代码库连接到远程服务器  
用法：git remote add [variable name] [Remote Server Link]  

删除本地与远程仓库的连接  
git remote remove [remote name]  

重命名  
git remote rename [rename]

# git push

将主分支上提交的变更发送到远程代码库  
用法：git push [variable name] master  

将指定分支上的提交发送到远程代码库  
用法：git push [variable name] [branch]  

将所有分支发送到远程代码库  
用法：git push –all [variable name]  

删除远程代码库上的一个分支  
用法：git push [variable name] :[branch name]  

使用SSH克隆下来的仓库，在push时需要提供安全认证，（生成安全认证文件/公钥文件）  
生成安全证书：ssh-keygen -t rsa -C[SSH仓库地址]  
安全证书保存位置（默认，安全认证文件夹）：C:/用户/当前用户/.ssh  
复制本地安全认证文件内容，在GitHub或gitee平台设置SSH公钥

# git pull

获取远程服务器上的变更，并合并到你的工作目录  
用法：git pull [Repository Link]  

已在本地设置远程仓库  
git pull [远程仓库名称] [分支]  

# git stash

临时保存所有修改的文件  
用法：git stash save

恢复最近一次stash（储藏）的文件  
用法：git stash pop

显示stash的所有变更  
用法：git stash list

丢弃最近一次stash的变更  
用法：git stash drop

# git restore

没提交前误删除文件，从存储区域恢复至工作区  
git restore [file]

# git reset  

从stage中撤出指定的文件，但可以保留文件的内容  
用法：git reset [file]  

撤销指定提交之后的所有提交，并在本地保留变更  
用法：git reset [commit]

重置：当前的版本库重置到某一次提交（问题：丢失提交过程）  
丢弃所有的历史记录，并回滚到指定的提交  
用法：git reset –hard [commit号]  

# git revert

$ git log --oneline  
后版本号  
前版本号  

还原到 后版本号之前（不丢失中间的提交，相当于重新提交了一次 前版本）   
git revert [前版本号]