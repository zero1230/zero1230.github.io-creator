---
title: "JS对象"
date: 2019-09-21T14:30:52+08:00
draft: false
---

# JS对象
## 对象
### 定义
- 无序的数据激合
- 键值对的集合
  
### 写法
- let obj={'name':'frank','age':19}
- let obj=new Object({'name':'frank','age':19})

### 细节
- 键名就算引号省略了,还是字符串

## 删除对象的属性

- delete obj['name']
- 'name' in obj//表示查找obj对象是否有name的属性
- obj.hasOwnProperty('name')//表示查找obj自身的对象中是否有name属性，不包含原型中的属性。

## 查看对象的属性

- Object.keys(obj)
- console.log(obj)
- obj['name']
- obj.name//记住这里的name是字符串
- obj[name]//记住这里的name是变量


## 修改对象的属性
- 改自身obj['name']='jack'
- 批量修改自身 Object.assign(obj,{age:18,...})
- 改共有属性obj.__proto__['toString']='xxx'
- 改共有属性Object.prototype['toString']='xxx'
- 改原型obj.__proto__=common
- 改原型let obj=Object.create(common)
- 注:所有的__proto__代码都是强烈不推荐的
  
## 增加对象的属性
- 基本同上:已有属性则改;没有属性则增。

## 注意
### 'name' in obj和obj.hasOwnProperty('name') 的区别：
- in表示obj对象中是否包含name字符串这个键，如果原型链中也有name字符串这个属性名，也可以返回true
- hasOwnProperty则表示在obj对象中是否包含name字符串这个属性名。不从含原型链中查找。
  
  



