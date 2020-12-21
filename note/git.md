## git笔记

### 新建分支
1) 切换到基础分支，如主干

git checkout master

2）创建并切换到新分支

git checkout -b panda

git branch可以看到已经在panda分支上

3)更新分支代码并提交

git add *

git commit -m "init panda"

git push origin panda

### 删除分支
git branch -d dev20181018 删除本地分支
git push origin --delete dev20181018   删除远程分支

### 合并commit
git rebase -i HEAD~2    //对最近的两次commit进行rebase操作
将需要合并的commit 内容前面的pick改为squash

保存退出

再将代码push -f到远端即可

### 放弃本地修改，拉取远程代码
git fetch --all    //只是下载代码到本地，不进行合并操作
git reset --hard origin/分支名如master    //把HEAD指向最新下载的版本
git pull //可以省略

### 回退命令：
$ git reset --hard HEAD^         回退到上个版本
$ git reset --hard HEAD~3        回退到前3次提交之前，以此类推，回退到n次提交之前
$ git reset --hard commit_id     退到/进到 指定commit的sha码
强推到远程：
$ git push origin HEAD --force

### 打tag
git tag -a v1.0.1 -m 'publish first release on c_master!'
git push origin v1.0.1
### 删除tag
git tag -d v1.0.1
git push origin --d <tagname>

### 重新拉取fork远程源码
git remote add upstream fork仓地址
git pull upstream master
git reset --hard upstream/master
git push --force

### LF will be replaced by CRLF in 解决办法
git config core.autocrlf false

### 删除远程分支：
git push origin --delete dev20181018

