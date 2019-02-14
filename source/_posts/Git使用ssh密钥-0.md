---
title: Git使用ssh密钥
date: 2018-08-07 16:08:18
author: Emily
avatar: /images/touxiang.jpeg
authorDesc: 一个测试
tags: GitHub
categories: 资料
timestamp: 20180807160818
---

git支持https和git两种传输协议，github分享链接时会有两种协议可选。
可以使用命令 git remote -v 查看你当前使用的协议。
git使用https协议，每次pull, push都会提示要输入密码，使用git协议，然后使用ssh密钥，就能免去每次都输密码的麻烦。

步骤：
一、生成密钥对
二、设置远程仓库上的公钥
三、修改为git协议

---

#### 一、生成密钥对
先确认本机是否已经有公钥
打开Git Bash Here，查看ssh目录
```
$ cd ~/.ssh
$ ls
```
显示如下，有id_rsa和id_rsa.pub(或者是id_dsa和id_dsa.pub之类成对的文件)，有.pub 后缀的文件就是公钥，另一个文件则是密钥。
```
id_rsa  id_rsa.pub  known_hosts
```
如果没有，我们就建一个（未经实践）
```
$ ssh-keygen -t rsa -C "your_email@youremail.com"
```
```
Creates a new ssh key using the provided email # Generating public/private rsa key pair.

Enter file in which to save the key (/home/you/.ssh/id_rsa):
```
直接回车。然后提示输入密码（安全点就输入，也可以不输入）
```
Enter same passphrase again: [Type passphrase again]
```
完成之后
```
Your public key has been saved in /home/you/.ssh/id_rsa.pub.
The key fingerprint is: # 01:0f:f4:3b:ca:85:d6:17:a1:7d:f0:68:9d:f0:a2:db your_email@youremail.com
```
现在就生成了本地密钥对。

#### 二、设置远程仓库上的公钥
查看生成的公钥：
```
$ cat ~/.ssh/id_rsa.pub
```
```
ssh-rsa AAA324zaC1ycQC0X6L1zLL4VHuvGb8uhmReSUzgntvk434aJ/v7kOdJ/MTyBlWXFCR+1nKhXpHAZsMR3c8E7CjZNJA+
YZevY5UCvEg+umT7PHghKYaJwaCxV7sjCEAGDNXC26IBMdMgOluQjp6o6j2KAdtRBdCDS/QIU5TH1fiq9tITo/aXBvjZeD+gH/A
pkh/0GbO8VQLhfuieheuiwfbkiohORn8N7C9lOa/UW3hu43489htGFlBVQeTE/IGqhMS5PMln3 admin@admin-PC
```
登录github帐户。点击头像，然后 Settings -> 左栏点击 SSH and GPG keys -> 点击 New SSH key
title起个名字。key粘贴生成的公钥。

登录码云账户。点击头像，然后 设置 -> 左栏点击 SSH公钥
标题 起个名字。公钥 粘贴生成的公钥。

完成后验证一下是不是正常工作：
```
$ ssh -T git@github.com
```
看到如下内容，即设置成功：
```
Hi xxx! You've successfully authenticated, but GitHub does not # provide shell access.
```

如果出现异常，出现：
```
ssh: connect to host github.com port 22: Connection timed out
```
出现提示，输入“yes”回车即可。

别人说，在存放公钥私钥(id_rsa和id_rsa.pub)的文件里，新建config文本，内容如下：
```
Host github.com
User YourEmail@163.com
Hostname ssh.github.com
PreferredAuthentications publickey
IdentityFile ~/.ssh/id_rsa
Port 443
```
我直接按提示，未执行创建文本，记录下来或许以后用到。

#### 三、修改为git协议
以上两个步骤设置过后，不需要再次设置，此步骤按实际情况执行，如果项目使用协议为https则需要此步骤。
```查看使用的协议
$ git remote -v
```
使用https协议，显示如下：
```
origin https://github.com/someaccount/someproject.git (fetch)
origin https://github.com/someaccount/someproject.git (push)
```
登录GitHub复制SSH协议相应url，使用命令修改url
```
$ git remote set-url origin SSH协议url
```
再使用命令查看协议
```
origin  https://github.com/EmilyLee123/yLee123.github.io.git (fetch)
origin  https://github.com/EmilyLee123/yLee123.github.io.git (push)
```
切换成功，以后pull和push代码再也不用输入邮箱和密码。