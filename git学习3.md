# Git学习（三）分支与标签

[TOC]



## 一、分支的概念

分支就是从主线上分离出来进行另外的操作，而又不影响主线，主线又可以继续干它的事，是不是有点像线程，最后分支做完事后合并到主线上而分支的任务完成可以删掉了。

## 二、分支的基本操作

为了方便演示分支，先从远程仓库Github上面克隆一个仓库过来。

![image-20220616142722298](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616142722298.png)

### 2.1查看分支

（1）一般使用

> **git branch**

来查看本地仓库的分支。

![查看本地仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616143144970.png)

(2)可以使用

> **git branch -r**

来查看远程仓库的分支。

![查看远程分支](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616143329350.png)

（3）可以使用

> **git branch -a**

来查看所有的本地和远程的仓库。

![查看所有分支](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616143508399.png)

### 2.2创建、切换分支

1. 一般使用

   > **git branch 分支名**

来创建一个分支。

![创建新的分支](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616145049275.png)

2. 使用

   > git checkout  分支名

来修改分支。

![test分支](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616151029156.png)

在test分支上加了个One.java文件，并将它提交到本地仓库中。将分支切换到master分支就会出现下面的情况。

![test分支](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616151348660.png)

### 2.3推送至远程仓库

使用命令：

> **git push 远程仓库名 分支名**

将本地仓库分支推送到远程仓库。

![推送至远程仓库分支](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616152049985.png)

### 2.4合并分支

使用命令：

> **git merge 分支名** 

我们要将分支2合并到分支1，必须在分支1里面使用上面的命令。

![合并分支](C:\Users\Asus\AppData\Roaming\Typora\typora-user-images\image-20220616152610389.png)

### 2.5将新添加的文件推送

使用命令：

> git push 远程仓库名 分支名

将刚刚合并的分支推送到远程仓库。

![推送合并分支](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616153023620.png)

### 2.6删除分支

使用命令

> **git branch -d 分支名**（删除本地分支）
>
> 或者
>
> **git branch -D 分支名**（强制删除本地分支）（**不建议强制删除**）

删除本地仓库的分支。

![删除本地仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616153539146.png)

使用命令：

> **git push origin -d 分支名 **来删除远程仓库。

![删除远程仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616153938796.png)

### 2.7分支练习

![分支练习](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616154027007.png)

工作中的：https://www.csdn.net/tags/NtDaYg4sNzE4MC1ibG9n.html。

## 三、Git标签

### 3.1标签的概念

标签指的是某个分支在某个特定时间点的状态，通过标签可以很方便切换到标记时的状态。

### 3.2标签的操作

1. 创建标签

   使用：

   > **git tag (标签名)**

来创建标签。

![创建标签](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616161352406.png)

2. 列出已有标签

   使用：

   > **git tag**

来列出已有的标签。

![列出已有标签](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616161634115.png)

3. 查看标签信息

   使用：

   > **git show 标签名**

来查看标签信息。

![查看标签信息](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616161820369.png)

4.将标签推送到远程仓库中

使用：

> **git push 远程仓库名 标签**

来将标签推送到远程仓库。

![推送到远程仓库](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616162540294.png)

5. 检出标签

   新建一个分支。使这个分支指向某个tag。

   使用：

   > **git checkout -b [分支名] 标签名**

此时分支的内容与指向标签的内容一样。

![创建并切换分支](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616163110969.png)

**一般情况下，发布新版本等时刻就会用到标签，其他时刻比较少用。**

6. 删除标签

   使用：

   > **git tag -d 标签名**

来删除标签。

![删除本地标签](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616163446470.png)

7.删除远程标签

使用：

> git push origin :refs/tags/标签名

来删除远程标签。

![删除远程标签](https://cdn.jsdelivr.net/gh/yuzesheng/markdownpictures@main/img/image-20220616163824797.png)