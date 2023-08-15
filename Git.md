### 1 log
#### 1.1 查看某个文件的提交记录，使用如下命令：
```
git log 文件名
```
#### 1.2 查看文件的详细修改内容，使用如下命令：
```
git log -p 文件名
```
### 2 stash
#### 2.1 查看暂存区列表
```
git stash list
```
#### 2.2 保存当前改动到暂存区
```
git stash save 'message'
```
建议自己定义信息，避免忘记保存的是什么
#### 2.3 提取但不删除暂存区记录
```
git stash apply
```
如果要提取指定的进度，则是通过第一步查看之后获得类似 stash@{stash_id} 的标示，然后追加在上面命令后面
#### 2.4 提取并删除暂存区记录
```
git stash pop [stash_id]
```
#### 2.5 删除某个暂存区记录
```
git stash drop [stash_id]
```
#### 2.6 清空暂存区
```
git stash clear
```
### 3 .gitignore 不生效
在项目开发过程中，一般都会添加 .gitignore 文件，规则很简单，但有时会发现，规则不生效。  
原因是 .gitignore 只能忽略那些原来没有被track的文件，如果某些文件已经被纳入了版本管理中，则修改.gitignore是无效的。  
那么解决方法就是先把本地缓存删除（改变成未track状态），然后再提交。
```
git rm -r --cached .

git add .

git commit -m 'update .gitignore'
```
### 4 Your branch is ahead of 'origin/master' by N commits.
如果不需要保存本地的修改，则可以直接执行
```shell
git reset --hard origin/master;git pull
```
### 5 git 分支重命名
#### 5.1 没有推送到远程，本地修改
```shell
git branch -m oldName newName
```
#### 5.2 推送到远程，本地修改
```shell
git branch -m oldName newName
git push --delete origin oldName
git push origin newName
git branch --set-upstream-to origin/newName
```
### 6 git config
```shell
git config --list
git config --global user.name xxx
git config --global user.email xxx@xxx.com
```
### 7 git 删除本地分支并拉取远程最新代码
(1) 切换到其他分支，然后删除本地分支
```shell
git checkout 其他分支
git branch -D 待删除分支
```
(2) 重新拉取
```shell
git fetch origin 待删除分支:待删除分支
git fetch 仓库地址
git fetch 仓库地址 待删除分支
```
### 8 git 回退单个文件
(1) 进入到文件所在目录，或者能找到文件的路径，查看文件的修改记录
```shell
git log fileName
```
(2) 回退到指定版本
```shell
git reset ** fileName
```
(3) 提交到本地参考
```shell
git commit -m “提交的描述信息”
```
(4) 更新到工作目录
```shell
git checkout fileName
```
(5) 提交到远程仓库
```shell
git push origin 分支名
```