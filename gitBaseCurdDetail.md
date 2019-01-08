## clone 已有仓库
git clone URL
## 提交 
### git add 提交文件
通过 git add命令将文件加入暂存区 A，再通过 git commit命令
### git commit -m '备注'
### 添加成功后，可以通过 git log
### 进行 push
只要执行 push，GitHub 上的仓库就会被更新
## git init——初始化仓库
要使用 Git 进行版本管理，必须先初始化仓库。Git 是使用 g i t 
init命令进行初始化的
##   git status——查看仓库的状态
```
$ git status
# On branch master
#
# Initial commit
#
nothing to commit (create/copy files and use "git add" to track)
结果显示了我们当前正处于 master 分支下。关于分支我们会在不久
后讲到，现在不必深究。接着还显示了没有可提交的内容。所谓提交
（Commit），是指“记录工作树中所有文件的当前状态”。
尚没有可提交的内容，就是说当前我们建立的这个仓库中还没有记
录任何文件的任何状态。这里，我们建立 README.md 文件作为管理对
象，为第一次提交做前期准备。
$ touch README.md
$ git status
# On branch master
#
# Initial commit
## Untracked files:# (use "git add <file>..." to include in what will 
be committed)#
# README.md
nothing added to commit but untracked files present (use "git add" to 
track)
可以看到在 Untracked files 中显示了 README.md 文件。类似地，
只要对 Git 的工作树或仓库进行操作，git status命令的显示结果就
会发生变化。
#
# Initial commit
#
# Changes to be committed:
# (use "git rm --cached <file>..." to unstage)
#
# new file: README.md
#
将 README.md 文件加入暂存区后，git status命令的显示结
果发生了变化。可以看到，README.md 文件显示在 Changes to be 
committed 中了
```
**Untracked   files 未跟踪的文件**
如果只是用 Git 仓库的工作树创建了文件，那么该文件并不会被记
入 Git 仓库的版本管理对象当中。因此我们用 git status命令查看
README.md 文件时，它会显示在 Untracked files 里
**Initial commit**
加入暂存区但未提交的文件会显示在 initial commit里
## git add——向暂存区中添加文件
要想让文件成为 Git 仓库的管理对象，就需要用 git add命令将其
加入暂存区（Stage 或者 Index）中。暂存区是提交之前的一个临时区域
## git commit——保存仓库的历史记录
git commit命令可以将当前暂存区中的文件实际保存到仓库的历
史记录中。通过这些记录，我们就可以在工作树中复原文件。
### 记述一行提交信息
```
我们来实际运行一下 git commit命令。
$ git commit -m "First commit"
[master (root-commit) 9f129ba] First commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 README.md
-m 参数后的 "First commit"称作提交信息，是对这个提交的
概述
```
### 记述详细提交信息
```
刚才我们只简洁地记述了一行提交信息，如果想要记述得更加详
细，请不加 - m，直接执行 g i t c o m m i t命令。执行后编辑器就会启
动，并显示如下结果。
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
# On branch master
#
# Initial commit
#
# Changes to be committed:
# (use "git rm --cached <file>..." to unstage)
#
# new file: README.md
#
在编辑器中记述提交信息的格式如下。
● 第一行：用一行文字简述提交的更改内容
● 第二行：空行
● 第三行以后：记述更改的原因和详细内容
只要按照上面的格式输入，今后便可以通过确认日志的命令或工具
看到这些记录。
在以 #（井号）标为注释的 Changes to be committed（要提
交的更改）栏中，可以查看本次提交中包含的文件。将提交信息按格式
记述完毕后，请保存并关闭编辑器，以 #（井号）标为注释的行不必删
除。随后，刚才记述的提交信息就会被提交。
```
## 只显示指定目录、文件的日志
```
只要在 git log命令后加上目录名，便会只显示该目录下的日志。
如果加的是文件名，就会只显示与该文件相关的日志。
$ git log README.md
```
### 显示文件的改动
```
如果想查看提交所带来的改动，可以加上 - p参数，文件的前后差
别就会显示在提交信息之后。
$ git log -p
```
##  git diff
执行 git diff命令，查看当前工作树与暂存区的差别
```
diff --git a/hello.java b/hello.java
index b30f47d..0432869 100644
--- a/hello.java
+++ b/hello.java
@@ -1,5 +1,5 @@
 public static void main(String[] args){
 System.out.println("hello git");
-System.out.println("home 修改"); 
+System.out.println("home 修改---"); 修改但还未提交的  
 System.out.println("commit 不加 -m");
 }
# 这里解释一下显示的内容。“+”号标出的是新添加的行，被删除的行则用“-”号标出。我们可以看到，这次只添加了一行
```
##  git diff HEAD
**查看工作树和最新提交的差别**
