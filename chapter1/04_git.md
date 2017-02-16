## windows下安装Git  

windows版的Git可以从[https://git-for-windows.github.io](https://git-for-windows.github.io "windows版Git下载地址")下载，网速慢的可以百度国内的镜像下载。  

下载完成后，安装按默认选项安装即可。安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口（与cmd命令行窗口不同的是：git窗口里命令以`$`开头）的东西，就说明Git安装成功！  

***

## Git初始设置  

#### 设置用户信息

安装完成后需要设置用户名和邮箱地址，因为git是版本控制工具，可能是多人协作的，所以需要报家门。  

在命令行输入：  
````  
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"  
````  
`Your Name`是你要设置的用户名，`email@example.com`是你要设置的邮箱地址。  

使用`git config`命令的`--global`参数表示这台电脑上所有git仓库都将使用这个设置。如果需要对不同仓库指定不同的设置，则需要使用另外的参数。  

#### 创建版本库  

版本库又名仓库，英文repository，它是一个文件目录，Git管理着这个目录里面的所有文件，每个文件的修改、删除，Git都能跟踪，以便任何时刻都可以追踪历史，或者在将来某个时刻可以“还原”。

创建版本库的第一步要先有个文件目录（文件夹），可以自己用鼠标到想要的目录下创建，也可以在命令行窗口用`mkdir`命令创建，创建好目录后在用`cd`命令将命令行工具移动到新创建的目录下，操作如下：
````
$ mkdir newrepository  
$ cd newrepository  
````  
（`newrepository`是新创建的文件目录名称，这里是示例，实际使用时根据需要设置。）  

第二步，通过`git init`命令把这个目录变成Git可以管理的仓库:  
````
$git init  
````
返回以下结果以为这创建新版本库成功：
````
Initialized empty Git repository in .../newrepository/.git/
````  
***
## 版本控制   

在Git里，存放文件的地方有4个概念：工作区、暂存区、分支和远程仓库，Git的版本控制就是记录这4个地方的文件的变化，对这4个地方的文件进行备份与还原。  

#### 工作区  

工作区就是电脑中存放文件的文件夹，所有的文件的修改都是首先在这里进行的。  

#### 版本库  

工作区有一个隐藏目录`.git`，这个不算工作区，而是Git的版本库。版本库分两个部分，暂存区（stage）和分支。  

通过`git add *`命令可以将文件的修改提交到暂存区，再通过`git commit -m ""`命令可以将文件的修改提交到分支保存。  

注意，`*`可以是一个文件名，也可以是多个文件名，如果只是`*`，可以一次提交所有的工作区的修改。`commit` 命令中的双引号内是说明，对这次提交的修改进行备注。   

#### 暂存区和分支

Git记录的是文件的变化，暂存区只会记录一次变化，而分支会记录所有变化，并对每次提交到分支的变化进行编号管理，当我们开发过程中遇到问题，想要退回到某次变化的时候，就可以通过对分支指针的操作来实现。  

#### 远程仓库  

Git是个分布式版本控制工具，它可以在不同的电脑上对同一个项目进行版本控制。我们可以将一个版本库提交到一个服务器上，这样就建立了远程仓库，在别的电脑上可以从这个服务器上clone这个远程仓库，不同电脑上的版本库内容都可以提交到这个远程仓库，也可以从这个远程仓库下载内容，这样就可以由多人在不同地方对一个项目同步进行管理。  

#### 管理修改与版本控制   

|需求|命令|  
|:----|:-----|
|从工作区到暂存区|git add <span style="color:green;">file.txt</span>|
|暂存区到分支|git commit -m <span style="color:green;">"说明"</span>|  
|分支到远程仓库|git push origin <span style="color:green;">master</span>|   
|远程仓库到分支|git pull|  
|回退到上一版本|git reset HEAD^|
|回退到3个版本之前|git reset HEAD~<span style="color:green;">3</span>|
|清空暂存区|git reset HEAD|  
|清空工作区|git checkout -- <span style="color:green;">*</span>|  
|清空暂存区和工作区|git reset --hard HEAD|   

***

## 远程仓库交互  

####  连接远程仓库  

这里假定远程仓库在Github上，首先在Github上注册一个账号，这个就不做介绍了。注册好账户后通过以下几个步骤将电脑上的git账号与github上的账户建立连系：  

1. 打开Shell（Windows下打开Git Bash），创建SSH Key：  
````
$ ssh-keygen -t rsa -C "youremail@example.com"
````  

2. 然后在电脑用户主目录下找到`.ssh`目录（需要先设置能查看隐藏文件夹），找到`id_rsa.pub`文件，复制里面的内容。  

3. 登陆Github，点击`Setting`，找到`SSH and GPG keys`，再点击`New SSH key`,将`id_rsa.pub`的内容粘贴到`Key`文本框中，再设置个`Title`，最后点`Add Key`，这样就成功在远程仓库中添加了本地git账户的修改权限。  

4. 用`$ git remote add origin git@github.com:michaelliao/example.git`命令，将本地git仓库与github上远程仓库关联起来，之后就可以向github上远程仓库推送修改内容了。  

#### 推送内容至远程仓库  

`git push <远程主机名> <本地分支名>:<远程分支名>`是将本地暂存区内容推送到远程仓库的标准命令，一般默认分支是master，所以命令是这样：`git push origin master:master`。当本地分支与远程分支名是一样的时候，可以省略远程分支名，简写成`git push origin master`。
