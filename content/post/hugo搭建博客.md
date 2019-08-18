---
title: "hugo博客搭建"
date: 2019-08-16T14:30:52+08:00
draft: false
---

# hugo 博客搭建

## 安装 hugo

### mac 安装方式

使用命令
brew install hugo 然后 hugo version 查看版本号是否安装成功

### window 安装方式

去 hugo release 页面下载，然后解压，把 hugo.exe 放到 D:\Software\hugo\hugo.exe,把 D:\Software\hugo\加入到 PATH，重启终端，运行 hugo version 查看版本

## 快速搭建博客

查看官方文档搭建，进入 hugo 官网，点 quick start 快速开始,从 step2-step7 照抄，
得到一个 public 目录，这就是我们的博客站点。然后部署到 github 上。hugo -server 可以预览。在 public 目录下，git init，git add .,git commit -m ,然后关联远程仓库，git remote add origin git@github.com:xxxx/x.github.io.git ,然后 git push -u origin master 推到远程仓库。然后访问 XXX.github.io 就能访问搭建成功的博客了。
