---
layout: post
title: "Git教程"
date: 2016-07-13   
tag: 工具 
---

欠下的账总是要还的，早就听说git作为版本控制，却直到2个月前实习才真正使用它，第一篇博客就梳理下常用的git命令吧。
     
### 本地仓库

通过`git init`命令把当前目录变成Git可以管理的仓库：    

```
$ git init  
```      

就会创建一个 `.git` 隐藏文件，建好了一个空的仓库(empty Git repository)。

可以用`git status`查看状态，看看哪些文件被修改了：

```
$ git status
```

使用`git add`把要提交的所有修改放到暂存区(stage)：

```
$ git add .
# $ git add readme.txt
```

然后，执行`git commit`就可以一次性将暂存区的所有修改提交到本地仓库：

```
$ git commit -m "<message>"
```

如果文件已经提交过，也就是被改动的文件是tracked，但还未进入暂存区，可以将`git add`和`git commit -m`组合起来：
```
$ git commit -am "<message>"
```

### 远程仓库

先有本地库后，关联到远程库：

```
$ git remote add origin git@github.com:Keerlsm/Keerlsm.github.io.git
```

关联后，第一次推送分支的所有内容时，使用命令：

```
$ git push -u origin branch-name
```

此后，每次本地提交后，只要有必要，就可以使用命令`git push origin branch-name`推送最新修改：

```
$ git push origin branch-name
```

**直接克隆仓库到本地**      

```
$ git clone git@github.com:Keerlsm/Keerlsm.github.io.git
```

Git支持多种协议，包括https，但通过ssh支持的原生git协议速度最快。    


### 分支管理

Git鼓励大量使用分支：
查看分支：`git branch`
创建分支：`git branch <name>`
切换分支：`git checkout <name>`
创建+切换分支：`git checkout -b <name>`
在本地创建和远程分支对应的分支，使用`git checkout -b branch-name origin/branch-name`，本地和远程分支的名称最好一致
合并某分支到当前分支：`git merge <name>`
删除分支：`git branch -d <name>`   



<br>

转载请注明：[潘柏信的博客](keerlsm.github.io) » [点击阅读原文](http://keerlsm.github.io/2018/05/GitTutorial/)     

