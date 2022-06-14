title: GitHub博客搭建（二）
author: John Doe
tags: []
categories:
  - 博客搭建
date: 2022-06-12 14:57:00
---
## 创建仓库以及SSH配置

##### 1.登录[Github](https://github.com/)，点击Your repositories，进入仓库页面

  <img src="/images/img/GithubBlog2/1.png" width = 50%>
  
##### 2.点击New按钮，进入仓库创建页面。
  <img src="/images/img/GithubBlog2/2.png" width = 100%>
 
##### 3.填写仓库名，格式必须为<用户名>.github.io，然后点击Create repository。
 <img src="/images/img/GithubBlog2/3.png" width = 100%>
 
##### 4.使用SSH将本地git与远程的GitHub建立联系

###### 4.1鼠标右键，打开Git Bush，依次输入：
``` bash
$ git config --global user.name "Your Username"
$ git config --global user.email "Your Email Address"
```
Your Username和Your Email Address就是注册GitHub账号时的用户名和邮箱。因为使用仓库前，要通过Username和Email标明自己的身份。
###### 4.2继续使用Git Bush，依次输入如下两条命令：
``` bash
$ cd ~/.ssh
$ ssh-keygen -t rsa -C "Your Email Address"
```
<font color="#dd0000">注意：</font>在输入cd ~/.ssh时，如果提示：No such file or directory， 说明你是第一次使用Git，没有影响。

提示：cd ~/.ssh用来检查本机的ssh密钥，ssh-keygen -t rsa -C "Your Email Address用于生成新的SSH Key。

在出现如下提示后，直接回车
``` bash
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/your_user_directory/.ssh/id_rsa):【这里直接回车】
```
会提示输入密码：
``` bash
Enter passphrase (empty for no passphrase):【输入加密串】【加密串我们看不见，所以你输密码的时候不要以为没输入进去，你直接输入就好，输完密码按回车键确定就行】
Enter same passphrase again:【再次输入加密串】
```
<font color="#dd0000">注意：</font>这个密码会在你提交项目时使用，如果为空的话提交项目时则不用输入。
<font color="#dd0000">个人建议不输入密码</font>

key生成成功后，可以看到Your public key has been saved in /C:/Users/john/.ssh/id_rsa.pub. 找到ssh key保存的位置。

##### 5.添加 SSH Key 到 GitHub

###### 5.1 登录[Github](https://github.com/)。依次点击右上角的头像->Settings->SSH and GPG keys->New SSH key
 <img src="/images/img/GithubBlog2/4.png" width = 100%>
 
###### 5.2打开本地SSH Key并复制到github
使用Notepad++打开本地C:/Users/john/.ssh/id_rsa.pub文件，也就是刚才生成的SSH key。如果看不到这个文件，需要设置显示隐藏的文件。
<img src="/images/img/GithubBlog2/5.png" width = 100%>
将本地文件里的SSH key全选复制粘贴到刚刚GitHub上通过New SSH key创建的key方框里，Title随便写或者直接空着不写也可以，直接点击Add SHH key就好了。

###### 5.3打开Git Bash，输入ssh -T git@github.com，测试是否添加成功
出现如下提示，输入yes即可
``` bash
The authenticity of host 'github.com (192.30.255.113)' can't be established.
RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
Are you sure you want to continue connecting (yes/no)?
```
输入yes后会提示输入密码：
``` bash
Enter passphrase for key '/c/Users/User/.ssh/id_rsa':【这里的密码也是加密串】
```
当系统出现如下提示时，说明成功了
``` bash
Hi HandsomeSuperRed! You've successfully authenticated, but GitHub does not provide shell access.
```