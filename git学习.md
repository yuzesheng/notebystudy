# Git学习（一）本地仓库

**本文使用Github图床，可能有些图片无法正常展示**

## 一、历史背景**(可跳过)**

> Linux 系统整个项目组开始启用一个专有的分布式版本控制系统 BitKeeper 来管理和维护代码，BitKeeper 的东家 BitMover 公司也免费授权 Linux 社区使用这个版本控制系统。后来 BitMover 公司发现社区有人试图破解 BitKeeper 的协议，于是 BitMover 公司收了回 Linux 社区的免费使用权。这就迫使 Linux 开源社区（特别是 Linux 的缔造者 Linus Torvalds）基于使用 BitKeeper 时的经验教训，开发出自己的版本系统。
> 

## 二、SVN和Git**（了解一下）**

### 2.1 SVN

> SVN是集中式版本控制系统，版本库是集中放在中央服务器的。在开发人员工作的时候，用的都是自己电脑，所以首先需要从中央服务器下载最新的版本，然后进行开发，开发完成后需要把自己开发的代码提交到中央服务器。

![SVN模型图](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220612214306268.png)

> 缺点：1. 服务器单点故障。
>
> ​           2. 容错性差。

### 2.2 Git

> Git是分布式版本控制系统，分为两种类型的仓库：本地仓库和远程仓库。
>
> 本地仓库指的是开发人员自己电脑上的git仓库。
>
> 远程仓库指的是远程服务器上面的仓库。

![Git模型图](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/p20220612214417.png)

简单的工作流程介绍：

1. 从远程仓库中克隆代码到本地仓库。
2. 从本地仓库中check out （修改）代码，然后进行代码修改。
3. 在提交前先将代码提交到暂存区。
4. 提交到本地仓库。本地仓库中保存修改的各个历史版本。
5. 修改完成后，需要和团队成员共享代码时，将代码push到远程仓库。

## 三、Git

### 3.1 Git下载与安装

1. 到[**git官网**](https://git-scm.com/downloads)去下载，根据电脑的类型选择合适的版本。

   ![Git官网](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220612223856743.png)

2. 安装：点击安装包，除了路径之外其他都选择默认安装即可。如果在任意目录下看到Git GUI Here和Git Bash Here,说明安装成功。

![Git安装成功标识](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220612224302751.png)

### 3.2 Git常用命令

#### 3.2.1环境配置

我们安装完Git之后的第一件事一定是设置用户名称和用户email。每次Git提交都会使用该用户信息。（这个可以联想一下QQ,我们使用QQ时一定要先登录，登录完成后给好友发送信息，对方才知道是谁给他发送的消息）。

一般是用下面两个命令来设置环境：

> git config --global user.name "your name"
>
> git config --global user.email "your email"

设置完成后我们可以通过下面的命令可以查看配置信息：

> git config --list

此时，在配置信息中就会出现我们的user.name和user.email。

![git配置信息](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/p20220612225621.png)

或者在下面的目录中C:\Users\用户名中找到.gitconfig文件，打开后就能看到我们的配置信息了。

![config文件](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220612230318248.png)

![config内容](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/p20220612230517.png)

#### 3.2.2获取Git仓库

获取Git仓库可以使用命令**git init**来获取git仓库。

![创建新的文件夹](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220612231256910.png)

上图是一个空的文件夹，还不是一个Git仓库！！！在文件夹中右键点击任意位置，然后左键单击Git bash here打开命令窗口。输入上面的**git init**并且回车。

![初始化仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220612231639791.png)

就会自动生成.git文件。此时才是一个.git仓库。如果执行完上面的操作发现什么都没有，那是因为.git文件是一个隐藏文件，我们需要将隐藏文件显示出来：点击上面的查看，在隐藏的项目前面将√打上。

![查看文件](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220612231918675.png)

#### 3.2.3基本概念

> 1. 版本库：.git文件就是版本库，存储了许多信息包括配置信息，日志信息和文件版本信息。（这个文件一般别去动它！！！）
> 2. 工作区：包含.git文件夹的目录就是工作目录，主要用来存放代码。
> 3. 暂存区：.git文件夹中有很多的文件，其中有一个index文件就是暂存区(stage)。暂存区是一个临时保存修改文件的地方。

我们其实可以这样理解：

工作区是我们能修改或者查看的地方，假设我们在逛淘宝，淘宝琳琅满目的商品和各种评论就可以看做工作区。

暂存区是我们暂时存放修改文件的地方，可以看做是购物车。

版本库是存放我们的配置信息，日志信息和文件版本信息可以看做是淘宝的订单信息。

#### 3.2.4文件状态

git仓库里面的文件状态有untracked (未被Git跟踪) 和tracked(已被Git跟踪)两种状态。我们可以使用**git status**来查看文件状态。

1. untracked是我们自己创建的文件并且未被添加到暂存区的文件。

![新建文件Hello](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613000158609.png)

![查看状态](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613000259526.png)

2. tracked是已经在仓库中或者在暂存区中的文件。其中又分为：unmodified(未修改状态)、modified(已修改状态)和staged(暂存状态)。

以上都是git的状态，可以通过status来查看。

#### 3.2.5本地仓库操作命令

1. 查看文件状态：

   > 第一种方式：**git status**
   >
   > 第二种方式：**git status -s **

![文件新状态](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613001527758.png)

为了方便看上面说到的状态，我将Hello.java提交后再修改并添加到暂存区中，所以显示的是modified状态。还新建了一个Dog.java文件且未添加到暂存区，所以是untracked状态。

![另一种方式查看状态](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613002428148.png)

很明显第二种更加简便看到各个文件的状态。

2. 将文件加入到暂存区中：

   > **git add 文件名** 

![将文件添加到暂存区](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613002819407.png)

3. 将文件从暂存区取消暂存：

   > **git reset HEAD 文件名**

刚刚已经Dog.java文件添加到暂存区了，现在将它从暂存区中取消暂存。

![回退操作](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613003301033.png)

4. 将暂存区的文件提交到本地仓库：

   > **git commit -m "注释信息"**

刚刚已经将Hello.java文件添加到了暂存区，下面将它提交到本地仓库。

![提交文件](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613003726276.png)

提交完成后再查看状态就只有一个Dog.java文件了。

5. 删除文件：

   > **git rm 文件名 然后执行上面的提交操作**

   刚刚已经将Hello.java文件提交了，结果发现bug出现了，必须将它删除。

![删除文件](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613004217576.png)

![文件列表](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613004240854.png)

此时的文件彻底删除了。

6.将文件添加到忽略列表：

> **touch .gitignore**

Git使用.gitignore文件来创建保存git忽略文件。因为Windows系统无法直接创建该忽略文件，只能在git bash 命令行里面进行创建。

![创建忽略文件](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613004819319.png)

![忽略文件](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613004749658.png)

![在gitignore文件输入内容](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613010226898.png)

在忽略文件中输入上述内容表示忽略掉所有的以.txt结尾的文件。

![查看ignore](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613010413506.png)

从状态中可以看到，我的a.txt文件没有任何的状态，这是因为已经被git忽略掉了。

7. 查看日志文件：

   > **git log**

![查看日志](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/p20220613010706.png)

我们可以通过git log查看日志并且知晓历史操作。可以用来回退版本。