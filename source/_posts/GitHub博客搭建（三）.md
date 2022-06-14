title: GitHub博客搭建（三）
author: John Doe
tags: []
categories:
  - 博客搭建
date: 2022-06-12 15:36:00
---
## Hexo安装及配置

##### 1.Hexo安装
选择你的博客放置在哪个盘的哪个文件夹，在空白处单击鼠标右键，依然选择Git Bash here来打开Git命令行，并输入如下命令。
<img src="/images/img/GithubBlog3/1.png" width = 100%>

``` bash
npm install -g hexo-cli
```

##### 2.Hexo本地部署
``` bash
$ hexo init <folder>
$ cd <folder>
$ npm install
```
其中，<folder>是你要保存博客内容的文件夹的名字。我的文件夹的名字是JYblog，所以上面三个命令就是：
  
``` bash
$ hexo init JYblog
$ cd JYblog
$ npm install
```
##### 3.启动

``` bash
$ hexo generate
$ hexo deploy 
$ hexo server
```
系统会出现如下提示：
``` bash
INFO  Start processing
INFO  Hexo is running at http://localhost:4000/. Press Ctrl+C to stop.
```
这时在浏览器地址栏输入http://localhost:4000/ 就可以看到默认博客界面。
##### 4.将hexo部署到GitHub
###### 4.1安装hexo-deployer-git
``` bash
npm install hexo-deployer-git --save
```
###### 4.2修改根目录下的 _config.yml，配置 GitHub 相关信息

找到其中的deploy标签，修改成如图形式。注意将repo的用户名替换为自己的用户名
<img src="/images/img/GithubBlog3/2.png" width = 100%>
###### 打开 Git Bash进入创建的JYblog文件夹，依次输入以下命令：
``` bash
$ hexo clean
$ hexo generate
$ hexo deploy
```
浏览器访问 https://jiyongblog.github.io/ 部署成功











































































































