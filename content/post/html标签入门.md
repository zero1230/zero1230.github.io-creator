---
title: "html标签入门笔记1"
date: 2019-08-12T14:30:52+08:00
draft: false
---

# HTML 标签入门笔记 1

## HTML 发明者

是由蒂姆·伯纳斯-李 90 年左右创造发明的，发明了一套 html,url,http 规则。

## HTML 页面起手需要写的格式

```
<!DOCTYPE html>
<!-- 文档类型 -->
<html lang="en">
  <!-- 语言的标签，可以换成ch-ZN -->
  <head>
    <meta charset="UTF-8" />
    <!-- 文件的字符编码 -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <!-- 禁用缩放 -->
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <!-- 兼容手机，告诉ie的版本 -->
    <title>Document</title>
    <!-- 标题 -->
  </head>
  <body></body>
</html>
```

## 章节标签

标题 h1-h6

章节 section

文章 article

段落 p

头部 header

脚部 footer

主要内容 main

旁支内容 aside

划分 div

## 全局属性

所有标签都有的属性

class 表示类属性

contenteditable 表示可以编辑

hidden 隐藏属性

id 不到万不得已，不要使用，因为有 2 个标签 id 值都一样，也不会报错

style 样式属性

tabindex 可以使用 tab 键，上下移动。数值为 0 时，表示最后访问。为-1 表示永远访问不到

title 显示内容的标签

## 默认样式

html 会自带一些样式。因为那时候还没有 css，有些样式太难看，需要清楚样式。自定义一个 cssreset.css,如下

```
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
*::before,
*::after {
  box-sizing: border-box;
}
a {
  color: inherit;
  text-decoration: none;
}
input,
button {
  font-family: inherit;
}
ol,
ul {
  list-style: none;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
```

## 内容标签

ol+li 有序列表内容

ul+li 无序列表内容

dl+dt+dd 描述内容

pre 保留空格和回车

hr 水平线

br 换行

a 链接

em 语气强调

strong 更加强烈的强调

code 保持字体的对齐

quote 行内引用

blockquote 换行引用
