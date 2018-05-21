---
title: Hexo+GitHubPages搭建自己的博客
date: 2018-05-21 14:33:23
tags: [Hexo, GitPage]
categories: "环境搭建"
---

## 前言
如果基于博客平台申请博客，功能上会收到很大的限制，所以这里我们借助[Hexo](https://hexo.io/)+[GitHubPages](https://pages.github.com/)搭建我们自己的专属博客。

## 环境搭建主要步骤
1. 申请GitHub账户，并建立GitHubPages
2. 安装Node.js，Hexo
3. Hexo常用命令
4. 搭建自己的第一个博客

## 详细

### 1. 申请GitHub账户，并建立GitHubPages
作为前提，你需要有一个[GitHub](https://github.com/)的账户，详细申请步骤就不提了。下面我们只介绍怎么申请一个GitHubPages。

> Github Pages是Github免费提供给开发者的一款托管个人网站的产品，目前只能托管静态内容。

首先创建一个repository，名称为 **xxx.github.io**，其中xxx是你的Github的用户名，必须保持一致，后缀也必须是.io。
另外，还要点选（Initialize this repository with a README）生成初始页面。
![](/images/githubpages1.jpg)
![](/images/githubpages2.jpg)

### 2. 安装Node.js，Hexo
Github Pages提供静态页面的支持，但是如果写自己博客的时候，每次都要编辑HTML代码，实在是比较麻烦的一件事情，所以需要借助Hexo来编辑自己的博客内容。
> 什么是 Hexo？
Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

安装 Hexo 相当简单。然而在安装前，您必须检查电脑中是否已安装下列应用程序：
- Node.js  [Node.js官网](https://nodejs.org/en)
- Git  [Git官网](https://git-scm.com/)

如果您的电脑中已经安装上述必备程序，接下来只需要使用 npm 即可完成 Hexo 的安装。
``` 
$ npm install -g hexo-cli
```

### 3. Hexo常用命令 [详细请看这里](https://hexo.io/zh-cn/docs/)
安装完以后，就可以通过Hexo创建自己的博客了。
### 【建站】
``` 
$ hexo init myblog
$ cd myblog
$ npm install
```

### 【创建文章并编辑】
下面这个命令会创建一个MarkDown(.md)文件，我们只需要编辑这个MarkDown文件来撰写自己的博客内容。关于MarkDown的写法，请参照： [MarkDown教程](http://www.markdown.cn)
``` 
$ hexo new myfirstblog
```

> Markdown是一种可以使用普通文本编辑器编写的标记语言，通过简单的标记语法，它可以使普通文本内容具有一定的格式。

执行下面的命令，可以把MarkDown文件转换为HTML页面
``` 
$ hexo generate (可以简写为hexo g)
```

### 【编译】
执行下面的命令，自动启动一个Web服务，进行页面的预览，默认地址是http://localhost:4000
``` 
$ hexo server (可以简写为hexo s)
```

### 【部署】
最后，我们需要把我们的成果部署到自己的GithubPages上面。对于hexo来说，只需要执行下面的命令就可以了。
``` 
$ hexo deploy (可以简写为hexo d)
```

但是在执行这个命令之前，需要安装Node的git支持并配置Hexo的_config.yml。
``` 
npm install hexo-deployer-git --save
```

_config.yml (配置文件路径例： 上面的hexo init myblog执行后的myblog目录下)
``` 
deploy:
  type: git
  repository: https://user:password@github.com/xxx/xxx.github.io.git
  branch: master
```

### 4. 搭建自己的第一个博客

