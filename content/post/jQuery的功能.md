---
title: "jQuery的功能"
date: 2019-10-28T14:30:52+08:00
draft: false
---

# jQuery的功能
1.jQuery 如何获取元素
```
$(document) //选择整个文档对象

$('#myId') //选择ID为myId的网页元素

$('div.myClass') // 选择class为myClass的div元素

$('input[name=first]') // 选择name属性等于first的input元素

$('a:first') //选择网页中第一个a元素

$('tr:odd') //选择表格的奇数行

$('#myForm :input') // 选择表单中的input元素

$('div:visible') //选择可见的div元素

$('div:gt(2)') // 选择所有的div元素，除了前三个

$('div:animated') // 选择当前处于动画状态的div元素

```
2.jQuery 的链式操作是怎样的
```
$('div').find('h3').eq(2).html('Hello');
//分解开来
$('div') //找到div元素

.find('h3') //选择其中的h3元素

.eq(2) //选择第3个h3元素

.html('Hello'); //将它的内容改为Hello
```
3.jQuery 如何创建元素
```
$('<p>Hello</p>');

$('<li class="new">new list item</li>');

$('ul').append('<li>list item</li>');
```
4.jQuery 如何移动元素
```
$('div').insertAfter($('p'));
//把div元素移动p元素后面
```
5.jQuery 如何修改元素的属性
```
$(".demo").attr("_id","abc")//attr可以获取或者给demo上添加自定义的_id属性。

$(".demo").addClass("abc")
//修改class类名之类的

$(".demo").removeClass("abc")//删除class
```

