---
title: Git用法
date: 2018-07-24 13:49:35
author: Emily
avatar: /images/touxiang.jpeg
authorDesc: 一个测试
tags: GitHub
categories: 资料
timestamp: 20180724134935
---

Git用树来形容最贴切，大家都这么说。
首先要有个仓库（树干），私有的就是栽在自己的院子里的树，公有的就是栽在路边的树。
然后要有分支，master是主分支（树干），其他的分支（树枝）。
把有改变的代码（叶子）加到分支上，写上备注（这片叶子是我的，有什么特别之处）。
往上一推，合并到主干，就是一棵大了一点的树了，但树还是那棵树。
再加东西是把那棵长大一点的树再拖下来，继续插枝。

## 记录下操作步骤（以win为例）：
在需要推送的代码文件夹打开cmd。

### 查查自己在什么分支

```
$ git branch
```

### 创建分支

```
$ git checkout -b "分支名字"
```

### 将更改内容添加入分支

添加全部更改内容
```
$ git add .
```
添加部分更改内容
``` bash
$ git add 具体文件名
```

### 添加备注

``` bash
$ git commit -m "备注"
```

### 推送分支

``` bash
$ git push origin "分支名字"
```

### 到GitHub合并代码
end


## 拉取新代码

### 查查自己在什么分支

``` bash
$ git branch
```

### 切换到主分支上

``` bash
$ git checkout master
```

### 拉取代码

``` bash
$ git pull origin master
```