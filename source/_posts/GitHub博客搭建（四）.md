title: GitHub博客搭建（四）
author: John Doe
tags: []
categories:
  - 博客搭建
date: 2022-06-12 16:07:00
---
## Hexo Admin插件以及Hexo主题安装

##### 1.Hexo Admin安装
在你的hexo根目录下，打开git bash here输入以下代码进行安装
<img src="/images/img/GithubBlog4/1.png" width = 100%>
``` bash
npm install --save hexo-admin
```
浏览器输入网址:localhost:4000/admin 查是否安装成功
<img src="/images/img/GithubBlog4/4.png" width = 100%>

##### 2.Hexo主题安装

###### 2.1主题选择
GitHub上的Hexo主题： https://github.com/hexojs/hexo/wiki/Themes

Hexo官网主题：https://hexo.io/themes/

知乎上的主题推荐：https://www.zhihu.com/question/24422335
###### 2.2主题安装
每一种主题，一般应该都会有相关的使用说明，包括安装、个性化设置，这里以fexo为例介绍安装过程。
在你的hexo根目录下，打开git bash here输入以下代码进行安装
``` bash
$ git clone git@github.com:forsigner/fexo.git themes/fexo
```
如果设置了密码，系统会提示输入密码，如果没有设置密码，将直接下载。

###### 2.3主题部署
使用Notepad++打开网站根目录的_config.yml  修改theme: fexo。
<img src="/images/img/GithubBlog4/2.png" width = 100%>
<img src="/images/img/GithubBlog4/3.png" width = 100%>

###### 2.4主题验证测试
输入以下命令
``` bash
hexo clean
hexo generate
hexo deploy
hexo server 
```
浏览器输入 http://localhost:4000/ 看看自己的主题是否已经应用。












