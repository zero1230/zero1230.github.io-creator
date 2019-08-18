---
title: "html重点标签"
date: 2019-08-17T14:30:52+08:00
draft: false
---

# html 重点标签

## a 标签

### 属性

href 超链接

target

href 超链接，取值可以有网站，如//google.com,也可以路径，比如/a/b/c,a/b/c,index.html，./index.html,也可以伪协议，javascript：代码; mailto:邮箱地址，表示跳转邮箱。跳转电话为 tel:13xx...,也能跳转到知道 id 位置，#id 名称.

target 取值。
\_blank 表示跳转到新的页面。 \_self 表示在当前页面打开。\_top 表示在最顶层打开。\_parent 表示在当前页面的上一层页面打开。
target 取值为“xxx”时候，会在当前页面打开,window.name 可以知道该页面的 name 为 xxx,也可以指定 iframe 的 name 为 xxx 时，target 的值为 xxx 时，会在 iframe 页面打开网页。

## table 标签

table 标签相关是

table

thead

tbody

tfoot

tr 行

th 表头

td 数据

相关样式
table-layout
border-collapse
border-spacing

常用表格使用代码如下

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Document</title>
    <style>
      table {
        width: 500px;
        table-layout: auto;
        border-spacing: 0px;
        border-collapse: collapse;
        border: 2px solid red;
      }
      th,
      td {
        border: 1px solid blue;
      }
    </style>
  </head>
  <body>
    <table>
      <thead>
        <tr>
          <th></th>
          <th>小明</th>
          <th>小红</th>
          <th>小龙</th>
        </tr>
      </thead>

      <tbody>
        <tr>
          <th>语文</th>
          <td>90</td>
          <td>82</td>
          <td>77</td>
        </tr>
        <tr>
          <th>数学</th>
          <td>90</td>
          <td>82</td>
          <td>67</td>
        </tr>
        <tr>
          <th>英语</th>
          <td>92</td>
          <td>72</td>
          <td>77</td>
        </tr>
      </tbody>
      <tfoot>
        <tr>
          <th>合计</th>
          <td>200</td>
          <td>200</td>
          <td>200</td>
        </tr>
      </tfoot>
    </table>
  </body>
</html>
```

## img 标签

### 作用

发出 get 请求，展示一张图片

### 属性

alt /height 图片高度/width 图片宽度/src 图片来源路径

### 事件

onload 图片成功加载的事件/ onerror 图片失败加载的事件

### 响应式

max-width:100% 添加后，可以在手机上也能适配

## form 标签

### 作用：发 get 或 post 请求，然后刷新页面。

### 属性

action 发送的地址/autocomplete/method 发送方式/target 提交哪个页面

### 事件

onsubmit 只有含 submit 的标签才能触发事件

## input 标签

### 作用

让用户输入内容

### 属性

type:button/checkbox/email/file/hidden/number/password/radio/search/submit/tel

其他 name/autofocus/checked/disabled/maxlength/pattern/value/placeholder

### 事件

onchange/onfocus/onblur

### 验证器

Html5 新功能，可以在 input 属性中加入 require 验证等

常用代码例子

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Document</title>
  </head>
  <body>
    <form action="/xxx" method="POST" autocomplete="on" target="_blank">
      <input type="text" name="user" />
      <input type="submit" />
      <hr />
      <input type="radio" name="gender" />male
      <input type="radio" name="gender" />female
      <hr />
      <input type="checkbox" name="hobby" />basket
      <input type="checkbox" name="hobby" />foot
      <input type="checkbox" name="hobby" />table
      <hr />
      <textarea
        name="text"
        style="resize: none ;width:100px;"
        cols="30"
        rows="10"
      ></textarea>
      <hr />
      <select name="date" id="">
        <option value="1">星期一</option>
        <option value="2">星期二</option>
      </select>
    </form>
  </body>
</html>
```

## 总结

使用标签，需要多写相关标签，多练才能熟悉用法。写的页面，不能直接打开文件，而是可以使用命令打开，如 http-serve . -c-1 命令打开。
