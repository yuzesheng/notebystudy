# Git学习（二）远程仓库

**（本文使用Github图床，可能有些图片无法正常展示）。**

## 一、常用的Git代码托管服务（远程仓库）

常见的Git代码托管平台有下面三种：

> 1. [github](https://github.com/)：全球最大的同性交友网站，里面有很多开源的项目，可以多参考大佬们的代码以提高自己。缺点是这个网站是在国外的，所以一般输入网址看到的一片空白或者错误，可以使用[Github的网络优化方法](https://blog.csdn.net/qq_43278189/article/details/120893149)来改善。
> 2. [码云](https://gitee.com/):是国内的一个代码托管平台，很多公司都使用这个来托管自己公司的代码。
> 3. [GitLab](https://about.gitlab.com/)是一个用于仓库管理系统的开源项目，使用[Git](https://baike.baidu.com/item/Git)作为代码管理工具，并在此基础上搭建起来的Web服务。

## 二、使用Github

### 2.1登录GitHub

浏览器中输入https://github.com/进入Github官网。

![Git官网](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613141128840.png)

如果说一直进不去，可以看看上面介绍时的优化方法。优化完一般就可以进去了。

进去之后如果有账号就点击sign in进行登录，没有的话就sign up注册一个就好了。

![Git登录页面](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613141654545.png)

![Git界面](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613141915150.png)

上面就是Github登录成功的界面了。

### 2.2新建仓库

我们可以在Github上面新建一个远程仓库。找到下面图片中的New就可以新建一个仓库了。

![新建仓库方式一](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613142304439.png)

或者使用右上角的**+**号来创建一个仓库。

![新建仓库方式二](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613142459420.png)

![创建仓库的具体方式](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613143109108.png)

### 2.3邀请其他成员成为仓库成员

Github不仅只是支持个人开发者，也可以通过邀请其他成员来实现团队开发。新建完仓库后，点击settings下面的collaborators(合作者)，通过**add people**按钮来实现成员添加。

![添加团队成员](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613144045292.png)

## 三、远程仓库操作

### 3.1初始化本地仓库：

> **git clone （url）**
>
> 通过上面的命令将远程仓库克隆到本地，克隆下来的文件直接就是仓库。

![克隆远程仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613145449577.png)

上面说过了克隆下来的直接就是仓库，所以里面就是.git文件。

![远程仓库初始化本地仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613150317121.png)

### 3.2查看远程仓库

通过以下三种方式来查看远程仓库

> 1. git remote
> 2. git remote -v
> 3. git remote show

通过上面三种方式来查看远程仓库。一般远程仓库默认名字是origin。

![查看远程仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613151016552.png)

### 3.3添加远程仓库：

可以通过命令：

> git remote add 仓库名字 url

来添加远程仓库。仓库名字一般默认是origin。

新建一个仓库Secondrepo并添加到远程仓库Secondrepo。

![新建Secondrepo仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613151911362.png)

![添加远程仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613151614357.png)

### 3.4移出远程仓库

一般可以使用

> git remote rm 仓库名字

从而将远程仓库删除。

![删除远程仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220613152325006.png)

### 3.5从远程仓库抓取

1. 从远程仓库获取有两种方式，一种是使用

> **git fetch 仓库名** 

![fetch文件](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616094902207.png)

但是这种方式从远程仓库拉取的所有分支的内容，但是并没有进行合并，所以会导致文件依旧是空白的，只需要合并就可以了。

![合并分支](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616095004677.png)

![提交文件](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616095216114.png)

2. 第二种方式是直接使用

   > **git pull**

直接将文件从远程仓库拉取文件，并且自动合并分支。**所谓的自动合并分支是和本地分支进行合并，而不是说远程分支进行合并,不要混淆了！！！**

![拉取文件](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616100821073.png)

拉取完成后查看一下本地仓库文件发现已经拉取到了。

这是正常情况的，但是如果说仓库中已经有文件了，还从远程仓库下拉文件，此时就会出现错误。

![拉取失败](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616104303037.png)

为什么会失败呢？这是因为假设你已经把readme文件提交到了本地仓库，如果下拉的文件里面也有readme文件，此时就会有覆盖掉的风险，那git作为一个版本控制软件，它并不知道你要的是哪个文件，于是它干脆让你拉取失败。

此时，我们只需要认可所谓的风险就可以抓取文件。可以使用下面的命令：

> **git pull --allow -unrelated-histories [远程仓库名] （分支名）** 

![下拉风险文件](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616104959336.png)

**所以，一般每天上班第一件事就是git pull!!!!可以省掉很多不必要的麻烦**

### 3.6推送到远程仓库

推送到远程仓库是指将我们的本地仓库推送到远程仓库，所以如果是更改的内容，一定要先提交到本地仓库，然后可以使用

> **git push (仓库名) （分支名）**

推送到远程仓库。

![新建b.txt文件](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616134835231.png)

上图表示新建了一个b.txt文件，下面将演示如何将本地文件提交到远程仓库。

1. 先把修改的的文件添加到暂存区

   ![添加暂存区](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616135301419.png)

2. 将文件提交到本地仓库

   ![提交到本地仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616135402870.png)

3. 推送到远程仓库

   ![推送到远程仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616135525605.png)

4.查看一下仓库看是否已经推送上来了

![验证结果](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616135644784.png)