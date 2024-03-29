---
title: "JS 的基本语法"
date: 2019-09-11T12:30:52+08:00
draft: false
---

# JS 的基本语法

## 表达式与语句

### 表达式

- 1+2 表达式的值为 3
- add(1,2)表达式的值为函数的返回值

### 语句

- var a =1 是一个语句

### 二者的区别

- 表达式一般都有值，语句有也可能没有
- 语句一般会改变环境(声明，赋值)
- 上面两句话不是绝对的

## 标识符

### 规则

- 第一个字符可以是 Unicode 字母或者\$或\_或中文
- 后面的字符，除上面所说，还可以有数字

## if 语句

### 语法

- if(表达式){语句 1}else{语句 2}
- {}在语句只有一句的时候可以省略，不建议这样做

### 变态情况

- 表达式里可以非常变态，如 a=1
- 语句 1 里可以非常变态，如嵌套的 if else
- 语句 2 里可以非常变态，如嵌套的 if else
- 缩进也可以很变态，如面试题常常下套

```
a=1
if(a===2)
    console.log('a')
    console.log('a等于2')
    //只打印a等于2，第2行的缩进可以打任意空格
```

## switch 语句

### 语法

```
switch(fruit){
    case "banana":
        //...
        break;
    case "apple":
        //...
        break;
    default:
        //...
}
```

### break 注意事项

- 大部分时候，省略 break 就完了，case 会穿透，执行多个 case 语句，直到 break 才结束执行
- 少部分时候，可以利用 break

### while 循环

### 语法

- while(表达式){语句}
- 判断表达式的真假
- 当表达式为真，执行语句，执行完在判断表达式的真假
- 当表达式为假，执行后面的语句

## for 循环

### 语法糖

-for 是 while 循环的方便写法

### 语法

- for(语句 1:表达式 2;语句 3){循环体}
- 先执行语句 1
- 如果为真，执行循环体，然后执行语句 3
- 如果为假，直接退出循环，执行后面的语句

## break 和 continue

break 在循环中，退出所有的循环。而 continue 则是退出当前的循环，后面的代码不执行，执行后面的循环。

## label 语句

### 语法

```
foo:{
    console.log(1);
    break foo;
    console.log('本行不会输出');
}
```

### 面试题

```
{foo:1}
```

在 chorme 浏览器中是一个对象，在火狐浏览器中则是一个标签，值为 1
