# Git  
- [windows下安装Git](#windows下安装Git)  
- [Git初始设置](#Git初始设置)  
  - [设置用户信息](#设置用户信息)  
  - [创建版本库](#创建版本库)  
- [版本控制](#版本控制)  
  - [工作区](#工作区)  
  - [版本库](#版本库)  
  - [暂存区和分支](#暂存区和分支)  
  - [远程仓库](#远程仓库)  
  - [管理修改与版本控制](#管理修改与版本控制)  
- [远程仓库交互](#远程仓库交互)  
  - [连接远程仓库](#连接远程仓库)  
  - [git remote](#git remote)  
  - [git clone](#git clone)  
  - [git push](#git push)  
  - [git fetch](#git fetch)  
  - [git pull](#git pull)  
- [分支管理](#分支管理)  
  - [创建分支](#创建分支)  
  - [保存分支合并记录](#保存分支合并记录)  
  - [保存现场](#保存现场)  
- [冲突处理](#冲突处理)  
- [标签管理](#标签管理)  
- [忽略特殊文件](#忽略特殊文件)  
- [git命令大全](#git命令大全)  

## windows下安装Git  

windows版的Git可以从[https://git-for-windows.github.io](https://git-for-windows.github.io "windows版Git下载地址")下载，网速慢的可以百度国内的镜像下载。  

下载完成后，安装按默认选项安装即可。安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口（与cmd命令行窗口不同的是：git窗口里命令以`$`开头）的东西，就说明Git安装成功！  


## Git初始设置  

### 设置用户信息

安装完成后需要设置用户名和邮箱地址，因为git是版本控制工具，可能是多人协作的，所以需要报家门。  

在命令行输入：  
````  
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"  
````  
`Your Name`是你要设置的用户名，`email@example.com`是你要设置的邮箱地址。  

使用`git config`命令的`--global`参数表示这台电脑上所有git仓库都将使用这个设置。如果需要对不同仓库指定不同的设置，则需要使用另外的参数。  

[回到顶部](#git)   

### 创建版本库  

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

[回到顶部](#git)   

## 版本控制   

在Git里，存放文件的地方有4个概念：工作区、暂存区、分支和远程仓库，Git的版本控制就是记录这4个地方的文件的变化，对这4个地方的文件进行备份与还原。  

### 工作区  

工作区就是电脑中存放文件的文件夹，所有的文件的修改都是首先在这里进行的。  

[回到顶部](#git)   

### 版本库  

工作区有一个隐藏目录`.git`，这个不算工作区，而是Git的版本库。版本库分两个部分，暂存区（stage）和分支。  

通过`git add *`命令可以将文件的修改提交到暂存区，再通过`git commit -m ""`命令可以将文件的修改提交到分支保存。  

注意，`*`可以是一个文件名，也可以是多个文件名，如果只是`*`，可以一次提交所有的工作区的修改。`commit` 命令中的双引号内是说明，对这次提交的修改进行备注。   

[回到顶部](#git)   

### 暂存区和分支

Git记录的是文件的变化，暂存区只会记录一次变化，而分支会记录所有变化，并对每次提交到分支的变化进行编号管理，当我们开发过程中遇到问题，想要退回到某次变化的时候，就可以通过对分支指针的操作来实现。  


### 远程仓库  

Git是个分布式版本控制工具，它可以在不同的电脑上对同一个项目进行版本控制。我们可以将一个版本库提交到一个服务器上，这样就建立了远程仓库，在别的电脑上可以从这个服务器上clone这个远程仓库，不同电脑上的版本库内容都可以提交到这个远程仓库，也可以从这个远程仓库下载内容，这样就可以由多人在不同地方对一个项目同步进行管理。  

[回到顶部](#git)   

### 管理修改与版本控制   

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

[回到顶部](#git)   

## 远程仓库交互  

###  连接远程仓库  

这里假定远程仓库在Github上，首先在Github上注册一个账号，这个就不做介绍了。注册好账户后通过以下几个步骤将电脑上的git账号与github上的账户建立连系：  

1. 打开Shell（Windows下打开Git Bash），创建SSH Key：  
````
$ ssh-keygen -t rsa -C "youremail@example.com"
````  

- 然后在电脑用户主目录下找到`.ssh`目录（需要先设置能查看隐藏文件夹），找到`id_rsa.pub`文件，复制里面的内容。  

- 登陆Github，点击`Setting`，找到`SSH and GPG keys`，再点击`New SSH key`,将`id_rsa.pub`的内容粘贴到`Key`文本框中，再设置个`Title`，最后点`Add Key`，这样就成功在远程仓库中添加了本地git账户的修改权限。  

这样之后就可以通过一些命令与远程仓库进行交互了。  

[回到顶部](#git)   

### git remote  

为了便于管理，Git要求每个远程主机都必须指定一个主机名。  

与远程仓库交互的第一步是添加远程主机，`git remote add` 命令用于添加远程主机。

````
git remote add <主机名> <网址>  
````  

````
git remote add origin git@github.com:tangyubao/mountainlearn.git  
````  
`git@github.com:tangyubao/mountainlearn.git`是远程仓库的地址，上述命令的作用是向远程仓库添加一个主机名，一般默认是`origin`。  

`git remote`命令用于管理主机名。

不带选项的时候，`git remote`命令列出所有远程主机。  

````
git remote
origin  
````
使用-v选项，可以参看远程主机的网址。

````
git remote -v
origin  git@github.com:jquery/jquery.git (fetch)
origin  git@github.com:jquery/jquery.git (push)  
````   

上面命令表示，当前只有一台远程主机，叫做origin，以及它的网址。

克隆版本库的时候，所使用的远程主机自动被Git命名为origin。如果想用其他的主机名，需要用git clone命令的-o选项指定。
````
$ git clone -o jQuery git@github.com:jquery/jquery.git
$ git remote  
jQuery  
````  

上面命令表示，克隆的时候，指定远程主机叫做jQuery。

`git remote show`命令加上主机名，可以查看该主机的详细信息。
````
git remote show <主机名>  
````

git remote rm命令用于删除远程主机。
````
git remote rm <主机名>  
````  

git remote rename命令用于远程主机的改名。
````
$ git remote rename <原主机名> <新主机名>  
````   

[回到顶部](#git)   

###  git clone  

如果我们将远程仓库已有的项目拷贝到本地来，这时就要用到`git clone`命令。
````
$ git clone <版本库的网址>  
````   

比如，克隆jQuery的版本库。  

````
git clone git@github.com:jquery/jquery.git  
````  

该命令会在本地主机生成一个目录，与远程主机的版本库同名。如果要指定不同的目录名，可以将目录名作为`git clone`命令的第二个参数。  

````
git clone <版本库的网址> <本地目录名>  
````  

git clone支持多种协议，有HTTP(s)、SSH、Git、本地文件协议等。  

通常来说，Git协议下载速度最快，SSH协议用于需要用户认证的场合。  

[回到顶部](#git)   

### git push  

`git push <远程主机名> <本地分支名>:<远程分支名>`是将本地暂存区内容推送到远程仓库的标准命令，一般默认分支是master，所以命令是这样：`git push origin master:master`。  

当本地分支与远程分支名是一样的时候，可以省略远程分支名，简写成`git push origin master`。  

如果当前只有一个本地与远程仓库只有一个相连接的分支，则推送命令可以进一步简化为`git push`。  

如果当前本地分支与多个主机存在连接关系，或第一次向远程仓库推送更新，则要使用`-u`选项制定一个默认主机，之后在不变更主机连接的情况下，则只用`git push`命令即可：  

````
git push -u origin master
````    
[回到顶部](#git)   

###  git fetch  

一旦远程主机的版本库有了更新(Git术语叫做commit)，需要将这些更新取回本地，这时就要用到`git fetch`命令。  

````
git fetch <远程主机名>  
````

上面命令将某个远程主机的更新，全部取回本地。

默认情况下，`git fetch`取回所有分支(branch)的更新。如果只想取回特定分支的更新，可以指定分支名。
````
git fetch <远程主机名> <分支名>  
````

比如，取回origin主机的master分支。
````
git fetch origin master  
````  

所取回的更新，在本地主机上要用“远程主机名/分支名”的形式读取。比如origin主机的master，就要用origin/master读取。

`git branch`命令的`-r`选项，可以用来查看远程分支，`-a`选项查看所有分支。
````
git branch -r
origin/master

git branch -a
* master
  remotes/origin/master  
````  

上面命令表示，本地主机的当前分支是master，远程分支是origin/master。

取回远程主机的更新以后，可以在它的基础上，使用git checkout命令创建一个新的分支。  

````
git checkout -b newBrach origin/master  
````  

上面命令表示，在origin/master的基础上，创建一个新分支。

此外，也可以使用git merge命令或者git rebase命令，在本地分支上合并远程分支。
````
git merge origin/master  
````  

或者：  
````
git rebase origin/master  
````  

[回到顶部](#git)   

### git pull  

`git pull <远程主机名> <远程分支名>:<本地分支名>`是取回远程仓库分支更新的标准命令，一般默认分支是master，所以命令是这样：`git pull origin master:dev`。  

如果远程分支是与当前分支合并，则冒号后面的部分可以省略：

````
git pull origin dev
````

上面命令表示，取回origin/dev分支，再与当前分支合并。实质上，这等同于先做`git fetch`，再做`git merge`。

````  
git fetch origin  
git merge origin/dev  
````  

在某些场合，Git会自动在本地分支与远程分支之间，建立一种追踪关系。比如，在`git clone`的时候，所有本地分支默认与远程主机的同名分支，建立追踪关系，也就是说，本地的master分支自动“追踪”`origin/master`分支。

Git也允许手动建立追踪关系。  

````
git branch --set-upstream master origin/dev
````  

上面命令指定master分支追踪origin/dev分支。

如果当前分支与远程分支存在追踪关系，git pull就可以省略远程分支名。

````
git pull origin  
````  

上面命令表示，本地的当前分支自动与对应的origin主机“追踪分支”进行合并。

如果当前分支只有一个追踪分支，连远程主机名都可以省略，简略为`git pull`，表示当前分支自动与唯一一个追踪分支进行合并。  

[回到顶部](#git)   

## 分支管理  

Git拥有强大的分支管理，通过分支，Git让多人协作开发变的容易。  

### 创建分支  

开始我们使用Git的时候只有一个分支，通常这个分支名叫`master`，在项目开发中，一般将`master`分支做为对外发布的最稳定的版本，在`master`之外再新建其他分支。  

标准的新建分支的格式是`git branch`加上分支名，例如：  
````
git branch dev
````
这样就新建了一个叫`dev`的分支，这个分支名一般代表开发版本。  

新建分支名后我们可以使用`git checkout dev`切换到`dev`分支上。  

我们也可以将这个两个命令集合在一起使用：  
````
git checkout -b dev  
````  

`git branch`不带任何参数的命令用于查看仓库里所有分支，带`*`的是当前分支。  

分支的目的是对项目更好的开发，当一个分支完成了任务之后，就需要将它合并的主分支`master`上。我们先用`git checkout master`命令切换到`master`分支，可以看到`dev`的更新内容消失了，这时我们再用`git merge`命令可以将制定分支合并到当前分支上：

````
git merge dev
````

合并之后，如果`dev`不再需要的话，可以将它删除：
````
git branch -d dev  
````
在没有合并的情况下删除分支的话，Git会提示错误，这就需要用`git brancch -D dev`来强制删除。  

除了上述参数命令外，`git branch`还有几种常见参数用法：  

查看所有远程分支：
````
git branch -a
````

重命名分支：  
````
git branch -m oldbranch newbranch  
git branch -M oldbranch newbranch
````
`-m`参数用来重命名分支，如果newbranch名字分支已经存在，则需要使用`-M`强制重命名。  

[回到顶部](#git)    

### 保存分支合并记录  

合并分支时，Git默认会用`Fast forward`模式，但这种模式下，删除分支后，会丢掉分支信息。

如果要强制禁用`Fast forward`模式，Git就会在`merge`时生成一个新的commit，这样，从分支历史上就可以看出分支信息。  

````  
git merge --no-ff -m "用no-ff参数合并分支" dev
````
因为本次合并要创建一个新的commit，所以加上`-m`参数，把commit描述写进去。这样可以在用，在`dev`分支被删除后，以后可以`git log`查看到在哪里进行了合并。   

[回到顶部](#git)   

### 保存现场  

有时候我们的工作计划还没有完成，但又有新的任务，必须立刻创建新的分支开始工作，因为原有的计划还没有完成，还不能提交，这时候我们就需要通过`git stash`命令来保存工作现场。  

分支任务完成后，切回至原分支，再恢复工作现场：  
````
git stash apply stash@{0}
````  
`apply`命令仅恢复现场，大多时候我们在恢复现场之后这个现场就没用了，就需要删除：  
````
git stash drop stash@{0}
````  

我们可以用一个命令完成恢复和删除现场的操作：  
````
git stash pop stash@{0}
````  
如果有多个现场保存了，我们可以使用`git stash list`命令查看所有现场，再通过参数`stash@{0}`的不同来选择恢复到制定现场。如果只有一个现场，则可以省略参数`stash@{0}`。

[回到顶部](#git)   

## 冲突处理  

有些情况下会出现内容冲突，比如合并分支的时候，比如向远程仓库推送更新，缺发现远程分支也有新的内容的时候。这时候就需要对冲突进行处理。  

通常出现内容冲突之后Git用`<<<<<<<`、`=======`、`>>>>>>>`标记出不同分支的内容,在`=======`前面的是当前分支的内容，在`=======`后面的是合并分支的内容，我们可以对这些内容进行修改处理，并删掉`<<<<<<<`、`=======`、`>>>>>>>`标记，然后再用`git add`和`git commit`提交就可以了。  

如果是要向远程仓库推送更新的话，完成上述工作之后再用`git push`推送即可。  

[回到顶部](#git)   

## 标签管理  

commit编号太复杂，不容易记，于是有了标签功能。  

标签一般用在`master`分支和`dev`开发分支上，创建标签非常容易：  
````
git tag v1.0 cf645d9  
````  
`v1.0`就是标签名，`cf645d9`是commit编号，这个命令的功能是在`cf645d9`上创建`v1.0`标签。  

如果不加commit编号，则默认在最新提交的commit上建立标签。  

`git tag`任何参数的命令是查看所有标签的。需要注意的是，所列出来的标签不是按时间顺序排序的，而是按字母排序的。  

使用`git tag show v1.0`可以查看`v1.0`标签的信息。  

用`-m`参数可以在创建标签的时候添加说明信息，`-a`用来指定标签名：  
````
git tag -a v0.1 -m "第一个预览版本" cf645d9
````

可以通过以下命令对标签进行一些常规操作：  
- `git push origin <tagname>`可以推送一个本地标签；

- `git push origin --tags`可以推送全部未推送过的本地标签；

- `git tag -d <tagname>`可以删除一个本地标签；

- `git push origin :refs/tags/<tagname>`可以删除一个远程标签。

[回到顶部](#git)   

##  忽略特殊文件  

有些文件可能很重要，我们需要放在Git工作目录中，但是又不能提交到远程仓库，这就需要在git工作根目录创建一个`.gitignore`文件，文件里写上你要忽略的文件的文件名，形式如下：
````
# Windows:
/chapter2/
!/chapter2/*.md
Thumbs.db
ehthumbs.db
Desktop.ini

# Python:
*.py[cod]
*.so
*.egg
*.egg-info
dist
build

# My configurations:
db.ini
deploy_key_rsa
````  
`chapter2`是忽略这个chapter文件夹。  

`*.so`是忽略所有扩展名为.so的文件。  

`!/chapter2/*.md`是将文件夹chapter2下所有扩展名为.md的文件添加到版本管理中，不忽略。   

有些时候，你想添加一个文件到Git，但发现添加不了，原因是这个文件被`.gitignore`忽略了，如果我们依然想添加这个文件，可以用带`-f`参数的`git add -f`命令来添加。  

或者你发现，可能是`.gitignore`写得有问题，需要找出来到底哪个规则写错了，可以用`git check-ignore`命令检查：

`git check-ignore -v hello.html`  

[回到顶部](#git)   

## git命令大全  
待完成
