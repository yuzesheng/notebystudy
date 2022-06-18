# Git学习（四）

[TOC]



## 一、TortoiseGit软件的使用

### 1.1下载与安装

进入[官网](https://tortoisegit.org/)选择合适的版本去下载软件。

![Toryoise软件官网](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616165123113.png)

选择合适的路径来安装软件，其他的默认就好了。完成安装后，在任意目录中点击右键都会出现下面的标识。

![安装成功标识](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616165526586.png)

**值得注意的是：如果使用的是SSH协议来传输，而TortoiseGit软件和Git软件在SSH上有冲突，需要将TortoiseGit的SSH.exe替换为Git路径的SSH.exe。

![替换SSH.exe](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616170615063.png)

### 1.2软件的使用

#### 1.2.1、创建仓库与克隆仓库

1. 如果是创建仓库，则先要创建文件夹，然后进入文件夹点击右键，选择 Git Create....就可以创建仓库了。

![创建仓库与克隆仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617092300866.png)

![初始化仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617092336591.png)

2. 如果要从远程仓库获取文件，则必须要先得到远程仓库的地址，然后在要放该仓库的地方点击右键选择Git Clone....

![克隆文件](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617102510434.png)

![下载下来的仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617102943683.png)

（**这个是别人的仓库，我只是演示一下克隆**）

#### 1.2.2将文件添加到暂存区

修改完成后的文件，点击右键选择小乌龟点击add就可以将文件从工作区添加到暂存区了。

![添加文件到暂存区](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617105533136.png)

![添加暂存区成功](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617105743796.png)

#### 1.2.3提交文件到本地仓库

只需要选中暂存区的文件，右键选择Git commit...在上边的输入栏里面输入一些注释信息就可以了。

![提交文件](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617110125398.png)

#### 1.2.4推送本地仓库到远程仓库

空白处点击右键，找到小乌龟如何点击Push推送。

![image-20220617113248831](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617113248831.png)

然后会看到下面的页面，此时我们需要指定远程仓库，和我们用命令添加远程仓库一样，只是现在是图形界面。

![推送页面](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617113412227.png)

![添加远程仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617114632573.png)

![上传成功](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617114915284.png)

#### 1.2.5推送本地仓库到远程仓库

首先从远程仓库克隆一个repo2到本地上。

![克隆repo2](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617115456480.png)

![推送仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617115903831.png)

由于是从远程克隆过来的，此时已经知道了远程仓库的信息。所以远程仓库就不用配置了，但是分支可以根据自己的需要进行更改。

![推送配置](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617115953107.png)

![查看上传是否成功](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617120304925.png)

#### 1.2.6拉取、创建分支、切换分支、合并分支

1. 拉取

   在文件空白处点击右键，找到小乌龟然后选择pull。在pull设置里面填上远程仓库的名字以及分支名字就可以了。

   ![下拉操作](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617121406176.png)

![拉取成功](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617121810140.png)

2. 创建分支

   在文件空白的地方点击右键找到小乌龟，然后选择create Branch...来创建分支。

![创建分支](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617120940830.png)

3. 切换分支

   在文件空白处右键找到小乌龟然后点击Switch/...然后输入即将切换的分支的名字来切换分支。

   ![切换分支选项](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617122542560.png)

![切换分支](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617122329716.png)

4. 合并分支

在文件空白处右键找到小乌龟然后点击Merge来合并分支。

![合并分支](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617122505832.png)

![合并完成](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617122649652.png)

#### 1.2.7推送指定分支到远程仓库

也是同样的上推操作只需要在上推的本地分支和远程分支以及远程仓库指定好就可以了。

![先找到提交路径](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617160634826.png)

![将指定分支提交到远程指定分支](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617160730285.png)

![检查是否成功](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617160846621.png)

## 二、在IDEA中使用git

### 2.1 IDEA中配置Git

在Idea中找到Settings

![Settings](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617161614258.png)

直接在搜索栏中输入Git或者知道它肯定是版本控制工具，所以找到Version Control就能找到Git了。往右边的Path to Git...输入Git安装路径。

![配置Git路径](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617162055871.png)

点击右边的test可以测试是否安装成功。

![测试是否安装成功](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617162005073.png)

此时出现版本信息说明安装成功了。

### 2.2 在Git中配置GitHub

上面已经配置好了Git,然后配置Github。由上面的图也可以发现Git相邻的就是GitHub了。

![配置Github](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617163154220.png)

添加Github账号。

![添加Github账号](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617163234337.png)

输入用户名和密码点击Log In就可以了。**（但是GitHub是国外的，很有可能登录不上去，所以可以使用token（令牌）的方式）可以参考一下别人的做法:https://blog.csdn.net/qq_41728540/article/details/115318085**

![输入登录信息](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617163349212.png)

### 2.3 将文件添加到暂存区并且提交文件

#### 2.3.1新建一个简单的Maven工程

![maven工程](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617172045763.png)

#### 2.3.2创建git仓库

![创建本地仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617174207726.png)

#### 2.3.3创建.gitignore文件

![.gitignore文件](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617173248805.png)



#### 2.3.4将一些要忽略的文件放到.gitignore文件中

.idea放的文件是Idea的文件，target放的是编译后的输出文件。

![image-20220617173708259](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617173708259.png)

#### 2.3.5将文件添加到暂存区并提交给本地仓库

![添加到暂存区](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617174444658.png)

![提交到本地仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617174710177.png)

值得注意的是，我们必须先选中整个项目再执行上面的操作。

#### 2.3.6推送到远程仓库

![找到push](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617175514617.png)

![点击push](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617175607555.png)

点击difine remote 去定义远程仓库的名字和路径

![设置远程仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617180028459.png)

看到下面的内容说明已经推送成功了。

![推送成功标志](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617180202013.png)

![远程仓库的情况](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617180307413.png)

#### 2.3.7从远程克隆到本地仓库

![image-20220617180431743](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617180431743.png)

![克隆下来的仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617182608480.png)

#### 2.3.8从远程仓库拉取

![从远程仓库拉取东西](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617204604524.png)

![下拉配置](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617204708375.png)

![拉取成功](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617204804366.png)

#### 2.3.9 IDEA使用Git版本对比

对同一个文件的比较。比如a.txt更改了四次，可以通过对比知道每次都改动了什么。

![版本对比](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617210601229.png)

#### 2.3.10创建分支和切换分支

![找到branches](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617211122218.png)

![新建分支](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617211225451.png)

![创建work分支](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617211349863.png)

![在新分支多加了个Leader类](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617211951854.png)

#### 2.3.11 合并分支

![merge分支](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617212222999.png)

![成功合并分支](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617212433199.png)

## 三、使用SSH链接

### 3.1 SSH概念

>    SSH 为 [Secure Shell](https://baike.baidu.com/item/Secure Shell) 的缩写，由 IETF 的网络小组（Network Working Group）所制定；SSH 为建立在应用层基础上的安全协议。SSH 是较可靠，专为[远程登录](https://baike.baidu.com/item/远程登录/1071998)会话和其他网络服务提供安全性的协议。利用 SSH 协议可以有效防止远程管理过程中的信息泄露问题。-----copy from baidu;

### 3.2在git中使用SSH协议

首先必要要拿到公密钥，只有拿到公密钥才能够使用SSH协议。使用命令:

> **ssh - keygen -t rsa**

来获取公密钥。得到公密钥之后可以在windows系统里面看到生成了.ssh目录。

![SSH目录](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617213615576.png)

使用软件打开公钥（pub）文件，然后**ctrl + a**全选里面的内容，**ctrl + c**复制。

然后打开github网站，点击头像找到settings，点击进去找到ssh，然后新建一个将公钥黏贴就好了。

![settings](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617214016121.png)

![SSh界面](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617214056832.png)

![新建一个ssh连接](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617214121118.png)

![key](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220617214214475.png)

将刚刚复制的公钥黏贴到key里面，title可以不用管，如果你一定要搞可以输入用途，当个备注就可以了。

**GIT学习系列Over!!!!**