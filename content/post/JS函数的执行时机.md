---
title: "JS函数的执行时机"
date: 2019-09-26T14:30:52+08:00
draft: false
---

# JS函数的执行时机

```
let i = 0
for(i = 0; i<6; i++){
  setTimeout(()=>{
    console.log(i)
  },0)
}
```
- 上面的代码会打印出6个6。因为for循环6次后，才会执行setTimeout函数里的打印i数值6次，此时数值i变为6，所以打印6个6。

##  让上面代码打印0、1、2、3、4、5 的方法则如下
```
for(let i = 0; i<6; i++){
  setTimeout(()=>{
    console.log(i)
  },0)
}

```
- 因为JS在for和let一起用的时候会加东西，每次循环都会多创建一个i，所以打印出来0、1、2、3、4、5
- 当然也可以使用自执行函数实现，存下局部变量，代码如下
```
 for (var i=0; i<6; i++) {
	    	(function(i){
	        	setTimeout(() => console.log(i), 0)
	    	})(i)
	    }

```
  


