---
title: "CSS 知识总结"
date: 2019-09-08T14:30:52+08:00
draft: false
---

# CSS 知识总结

## 浏览器渲染原理

    主要有如下步骤
    1.根据HTML构建HTML树
    2.根据CSS构建CSS树
    3.将两颗树合并成一颗渲染树
    4.Layout布局（文档流，盒模型，计算大小和位置）
    5.Paint绘制（边框颜色，文字颜色，阴影等画出来）
    6.Compose合成（根据层叠关系展示画面）

### 如何更新样式

    一般使用JS来更新样式，有三种更新方式
    1.全走，如div.remove()会触发当前消失，其他元素relayout
    2.第二种，跳过layout 改变背景色，只需composite
    3.跳过layout和paint 改变transfrom,只需composite

## CSS 动画的两种做法

### 1.transition 过渡

作用:补充中间帧
语法:

    transition:属性名(如width,all) 时长(1000ms) 过渡方式(linear|ease) 延迟

注意：不是所有属性都能过渡，如 display:none=>block 无法过渡

### 2.animation

声明关键帧

添加动画

使用写法如下

```
@keyframes xxx{
    0%{transform:scale(1)}
    100%{transform:scale(1.2)}
}

```

animation 缩写语法:时长(1s 或者 1000ms)|过渡方式(linear)|延迟|次数(infinite)|方向(reverse|alternative|alternative-reverse)|填充模式(none|forwards|backwards)|是否暂停(paused|running)|动画名;

### 3.画一个跳动的红心来实践下

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Document</title>
    <style>
      #heart {
        margin: 300px;
        position: relative;
        display: inline-block;
        animation: hear 1000ms infinite alternate-reverse linear;
        /* transition: all 1s; */
      }
      /* #heart:hover {
        transform: scale(0.5);
      } */

      @keyframes hear {
        0% {
          transform: scale(1);
        }
        100% {
          transform: scale(1.2);
        }
      }

      .left {
        position: absolute;
        height: 100px;
        width: 100px;
        background-color: red;
        transform: rotate(45deg) translate(-80px, 0px);
        border-radius: 50% 0 0 50%;
      }
      .right {
        position: absolute;
        height: 100px;
        width: 100px;
        background-color: red;
        transform: rotate(45deg) translate(0px, -80px);
        border-radius: 50% 50% 0% 0%;
      }
      .bottom {
        position: absolute;
        height: 100px;
        width: 100px;
        background-color: red;
        transform: rotate(45deg);
      }
    </style>
  </head>
  <body>
    <div id="heart">
      <div class="left"></div>
      <div class="right"></div>
      <div class="bottom"></div>
    </div>
  </body>
</html>

```

## 总结

css 的知识需要自己不断实践练习才能掌握了解。
