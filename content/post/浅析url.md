---
title: "浅析URL"
date: 2019-08-30T14:30:52+08:00
draft: false
---

# 浅析 URL

## URL 构成部分

协议+域名或 IP+端口号+路径+查询字符串+锚点
URL 举例：
https://www.baidu.com/s?wd=hello&rsv_spt=10#5

## DNS 的作用

可以解析域名，通过输入域名地址，会通过 dns 解析得到 IP 地址。可以使用 nslookup 域名地址来获取 IP 地址

## IP 的作用

IP 分为内网和外网。通过路由器划分内外网。IP 可以标示互联网上计算机的位置。可以使用 ping 网址，来获得对应的 IP 地址。

## 域名

域名就是对 IP 的别称。一个域名可以对应不同 IP,这叫负载均衡。一个 IP 可以对应不同域名，这叫主机共享。域名有以下分类。com，org 之类是顶级域名、baidu.com 为 2 级域名、www.baidu.com 为三级域名。
