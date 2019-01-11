# GigHub
[:coffee: Java](#coffee-java)
## SSH 秘钥
```
GitHub 上连接已有仓库时的认证，是通过使用了 SSH 的公开密钥
认证方式进行的。现在让我们来创建公开密钥认证所需的 SSH Key，并
将其添加至 GitHub。
ssh-keygen -t rsa -C "your_email@example.com"
验证时  第一次输入
输入要在其中保存密钥的文件（/c/users/lenovo/.ssh/id_rsa）
第二次 密码 第三次重复密码
id_rsa 文件是私有密钥，id_rsa.pub 是公开密钥。
```
|GigHub名词|名词解释|使用方式
|--------|--------|--------|
|Follow|关注|点击关注人的github 主页点击Follow|
|clone|克隆|
|Wiki|文档|
|Issue|问题|

## 创建仓库

### Description
Description 栏中可以设置仓库的说明。这一栏不是必需项，可以留空。
### Public、Private
在这一栏可以选择 Public 还是 Private。这里我们选择 Public，创建
公开仓库，仓库内的所有内容都会被公开。
选择 Private 可以创建非公开仓库，用户可以设置访问权限，但这项
服务是收费的
### Initialize this repository with a README
在 Initialize this repository with a README 选项上打钩，随后
GitHub 会自动初始化仓库并设置 README 文件，让用户可以立刻
clone 这个仓库。如果想向 GitHub 添加手中已有的 Git 仓库，建议不要
勾选，直接手动 push。
### Add .gitignore
下方左侧的下拉菜单非常方便，通过它可以在初始化时自动生
成 .gitignore 文件 A。这个设定会帮我们把不需要在 Git 仓库中进行版本管
理的文件记录在 .gitignore 文件中，省去了每次根据框架进行设置的麻
烦。下拉菜单中包含了主要的语言及框架，选择今后将要使用的即可。
由于本书中我们并不使用任何框架，所以不做选择。
### Add a license
右侧的下拉菜单可以选择要添加的许可协议文件。如果这个仓库中
包含的代码已经确定了许可协议，那么请在这里进行选择。随后将自动
生成包含许可协议内容的 LICENSE 文件，用来表明该仓库内容的许可
协议。
输入选择都完成后，点击 Create repository 按钮，完成仓库的创建
## README.md
README.md 在初始化时已经生成好了。README.md 文件的内容
会自动显示在仓库的首页当中。因此，人们一般会在这个文件中标明本
仓库所包含的软件的概要、使用流程、许可协议等信息。如果使用
Markdown 语法进行描述，还可以添加标记，提高可读性
## 下为 github学习笔记 
> * [github基础操作包括 add commit log diff push](https://github.com/lh1228216717/Hello-World/blob/master/gitBaseCurdDetail.md)
> * [github关于分支操作的笔记学习 包括显示 创建 合并 切换 恢复 消除冲突。。](https://github.com/lh1228216717/Hello-World/blob/master/gitBaseBranch.md)
