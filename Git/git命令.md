# git config
分别设置提交代码的用户名和电子邮件地址  
用法：git config –global user.name “[name]”  
用法：git config –global user.email “[email address]”

# git init
创建一个新的代码库  
用法：git init [repository name]

# git clone
通过指定的URL获取一个代码库  
用法：git clone [url]

# git add
将一个文件添加至stage(暂存区)  
用法：git add [file]  

将多个文件添加至stage(暂存区)  
用法：git add *

将全部变更文件添加至stage(暂存区)  
用法：git add .

# git commit
在版本历史记录中永久记录文件  
用法：git commit -m “[ Type in the commit message]”  

将提交git add命令添加的所有文件，并提交git add命令之后更改的所有文件  
用法：git commit -a

# git diff
显示尚未添加到stage的文件的变更  
用法：git diff  

显示添加到stage的文件与当前最新版本之间的差异
用法：git diff –staged  

显示两个分支之间的差异  
用法：git diff [first branch] [second branch]  

# git reset
从stage中撤出指定的文件，但可以保留文件的内容  
用法：git reset [file]  

撤销指定提交之后的所有提交，并在本地保留变更  
用法：git reset [commit]

丢弃所有的历史记录，并回滚到指定的提交  
用法：git reset –hard [commit]  

# git status
显示所有需要提交的文件  
用法：git status

# git rm
删除工作目录中的文件，并将删除动作添加到stage  
用法：git rm [file]

# git log
显示当前分支的版本历史记录  
用法：git log

显示某个文件的版本历史记录，包括文件的重命名  
用法：git log –follow[file]  

# git show
显示指定提交的元数据以及内容变更  
用法：git show [commit]

# git tag
给指定的提交添加标签  
用法：git tag [commitID]

# git branch
显示当前代码库中所有的本地分支  
用法：git branch

创建一个分支  
用法：git branch [branch name]

删除指定的分支
用法：git branch -d [branch name]

# git checkout
切换分支
用法：git checkout [branch name]

创建一个分支，并切换到新分支上  
用法：git checkout -b [branch name]

# git merge
将指定分支的历史记录合并到当前分支  
用法：git merge [branch name]

# git remote
将本地的代码库连接到远程服务器  
用法：git remote add [variable name] [Remote Server Link]

# git push
将主分支上提交的变更发送到远程代码库  
用法：git push [variable name] master

将指定分支上的提交发送到远程代码库  
用法：git push [variable name] [branch]

将所有分支发送到远程代码库  
用法：git push –all [variable name]

删除远程代码库上的一个分支  
用法：git push [variable name] :[branch name]

# git pull
获取远程服务器上的变更，并合并到你的工作目录  
用法：git pull [Repository Link]

# git stash
临时保存所有修改的文件  
用法：git stash save

恢复最近一次stash（储藏）的文件  
用法：git stash pop

显示stash的所有变更  
用法：git stash list

丢弃最近一次stash的变更  
用法：git stash drop