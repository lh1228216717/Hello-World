
## git branch——显示分支一览表
git branch命令可以将分支名列表显示，同时可以确认当前所在分支
```
$ git branch
* master
可以看到 master 分支左侧标有“*”（星号），表示这是我们当前所
在的分支。也就是说，我们正在 master 分支下进行开发。结果中没有显
示其他分支名，表示本地仓库中只存在 master 一个分支。
```
## git checkout -b——创建、切换分支
如果想以当前的 master 分支为基础创建新的分支，我们需要用到 git checkout -b命令
```
实际上，连续执行下面两条命令也能收到同样效果。
$ git branch feature-A
$ git checkout feature-A
```
## git 分支推送
```
git push origin 分支名称
```
## git merge——合并分支
## git reflog 
查看当前仓库执行过的操作的日志
## 过 git reset --hard 哈希码值
```
在日志中，我们可以看到 commit、checkout、reset、merge 等 Git 命
令的执行记录。只要不进行 Git 的 GC（Garbage Collection，垃圾回收），
就可以通过日志随意调取近期的历史状态，就像给时间机器指定一个时
间点，在过去未来中自由穿梭一般。即便开发者错误执行了 Git 操作，
基本也都可以利用 git reflog命令恢复到原先的状态，所以请各位
读者务必牢记本部分。
从上面数第四行表示 feature-A 特性分支合并后的状态，对应哈希值
为 83b0b94A。我们将 HEAD、暂存区、工作树恢复到这个时间点的状态。
$ git checkout master
$ git reset --hard 83b0b94
HEAD is now at 83b0b94 Merge branch 'feature-A'
之前我们使用 git reset --hard命令回溯了历史，这里又再次
通过它恢复到了回溯前的历史状态
```
##  消除冲突
分支合并时 出现 修改冲突文件 重新 add commit merge
## $ git commit --amend
```
执行上面的命令后，编辑器就会启动。
Fix conflict
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
# On branch master
# Changes to be committed:
# (use "git reset HEAD^1 <file>..." to unstage)
#
# modified: README.md
#
编辑器中显示的内容如上所示，其中包含之前的提交信息。请将
提交信息的部分修改为 Merge branch 'fix-B'，然后保存文件，关闭编
辑器
```
## git commit --amend——修改提交信息 
```

执行上面的命令后，编辑器就会启动。
这里是上次提交的信息
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
# On branch master
# Changes to be committed:
# (use "git reset HEAD^1 <file>..." to unstage)
#
# modified: README.md
#
```
## git commit -am '添加提交'

## git 切换分支时 遇到错误
+  The following untracked working tree files would be overwritten by checkout:         glshop-common/glshop-common.iml Please move or remove them before you switch branches. Aborting
+ 解决办法 git clean -d -fx
## 远程分支删除
+ 远程分支删除后使用 git remote prune origin
