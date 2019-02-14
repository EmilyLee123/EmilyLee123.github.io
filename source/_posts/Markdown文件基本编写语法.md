---
title: Markdown文件基本编写语法
date: 2018-08-07 17:50:56
author: Emily
avatar: /images/touxiang.jpeg
authorDesc: 一个测试
tags: 资料
categories: 资料
timestamp: 20180807175056
---
写blog需要使用Markdown，记录一些常用写法。

### 标题，最多6级：
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
####### 七级标题

### 列表：

无序号列表：
* 111
* 222
+ 111
+ 222
- 111
- 222

用*，+，-创建无序列表

有序号列表：
1. 列表1
2. 列表2
3. 列表3

数字后加英文.创建有序列表。

6. 序列1
4. 序列2
5. 序列3

序列根据第一行数字排序，与之后的列表数字无关。

### 区块：
> 要特别注意

> 一级块
>> 二级块
>>> 三级块

用法就是在语句前面加一个 > ，注意是英文的那个右尖括号，注意空格。

### 分割线
***
---
___
* * * *
-----
_ _ _

分割线可以由* - _（星号，减号，底线）这3个符号表示，注意至少要3个，且不需要连续，有空格也可以.

### 连接
[百度](http://baidu.com)

链接的文字放在[]中，链接地址放在随后的（）中。

### 图片
![图片](http://image.baidu.com/search/detail?z=0&word=%E6%91%84%E5%BD%B1%E5%B8%88%E8%8A%A6%E7%82%B3%E8%87%A3&hs=0&pn=1&spn=0&di=0&pi=55562477953&tn=baiduimagedetail&is=0%2C0&ie=utf-8&oe=utf-8&cs=4036622033%2C3062905213&os=&simid=&adpicid=0&lpn=0&fm=&sme=&cg=&bdtype=-1&oriquery=&objurl=http%3A%2F%2Fb.hiphotos.baidu.com%2Fimage%2Fpic%2Fitem%2Fd52a2834349b033bda94010519ce36d3d439bdd5.jpg&fromurl=&gsm=0&catename=pcindexhot&islist=&querylist=)

用法跟链接的基本一样，唯一的不同就是，图片前面要写一个！（这是必须的）。

### 代码框
单行

`git status`

多行

``` 注释
git status
git remote -v
```

单行代码两个反引号``括起来，多行代码3个反引号括起来，多行可写注释。

### 表格
|name|age|sex|
|:---:|:---|---:|
|Emily|20|F|
|lucy|18|M|

冒号代表对齐方式。

name|age|sex
-|-|-
Emily|20|F
lucy|18|M

### 强调
*字体倾斜*
_字体倾斜_

**字体加粗**
__字体加粗__

一个*或_包起文字，代表字体倾斜。
两个**或__包起文字，代表字体加粗。

### 转义
\\
\*
\#
\_

需要转义前加斜杠\

### 删除线
~~删除线~~

使用两个~包起文字