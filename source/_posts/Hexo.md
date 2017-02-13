---
title: Hexo - 简洁、高效的博客框架
date: 2017-02-12 23:27:44
tags:
---

### 安装配置

安装Hexo前提
- Node
- Git

安装hexo
========
``` 
$ npm install -g hexo-cli
```
创建项目
========
```
$ hexo init <folder>
$ cd <folder>
npm install
```
### hexo博客

新建文章
========
```
$ hexo new [layout] <title>
```
生成静态文件
========
```
$ hexo generate
//简写
$ hexo g
```
部署网站
========
```
$ hexo deploy
//简写
$ hexo d
```
启动服务器
========
默认端口为4000
``` 
$ hexo server
//简写
$ hexo s
```
清除静态文件缓存
========
```
$ hexo clean
```
安装Next主题
=======
```
$ git clone https://github.com/iissnan/hexo-theme-next themes/next
```
启用主题，更改系统配置文件
========
```
theme: next
```
hexo根目录下`_config.yml`为系统配置文件
主题根目录下`_config.yml`为主题配置文件

### 上传代码至GitHub

安装`hexo-deploy-git`插件，用于提交代码到GitHub

绑定GitHub地址，更改系统配置文件
========

```
deploy
	type：git
	repo：https://github.com/liugaoshuai/liugaoshuai.github.io.git
	branch：master
```

提交代码
========
```
$ hexo deploy
```
