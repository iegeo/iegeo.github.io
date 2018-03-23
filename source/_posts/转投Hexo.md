---
title: 转投Hexo
date: 2017-05-13 19:43:05
categories: "Hexo教程"
tags: 
    - hexo
---
闲的无事就注册了个Github账号,发现上面有一个pag功能。于是乎便想搭建一个静态站点。各种google了一些资料，决定用hexo来生成静态页面。

### Hexo简介
Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。
<!--more-->
### 安装前提
安装 Hexo 相当简单。然而在安装前，您必须检查电脑中是否已安装下列应用程序：

- [Node.js](http://nodejs.org/)
- [Git](http://git-scm.com/)

直接下载安装就行。

```bash
$ npm install -g hexo-cli
```
### 本地服务
安装 Hexo 完成后，请执行下列命令，Hexo 将会在指定文件夹中新建所需要的文件。
```bash
$ hexo init <folder>
$ cd <folder>
$ npm install
```
新建完成后，指定文件夹的目录如下：

```
.
├── _config.yml
├── package.json
├── scaffolds
├── source
|   ├── _drafts
|   └── _posts
└── themes
```
**_config.yml**
网站的 配置 信息，可以在此配置大部分的参数。

### server
```bash
$ hexo server
```
启动服务器。默认情况下，访问网址为： http://localhost:4000 。

### 完成后部署
可执行下列的任何一个命令，让 Hexo 在生成完毕后自动部署网站。
```bash
$ hexo g -d
$ hexo d -g
```

