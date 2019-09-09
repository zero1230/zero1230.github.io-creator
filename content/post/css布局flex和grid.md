---
title: "Css布局flex与grid"
date: 2019-08-31T14:30:52+08:00
draft: false
---

# flex 布局

## 常用代码

```
display:flex;
flex-direction:row/column;
flex-wrap:wrap;
justify-content:center/space-between;
align-items:center;
```

## flex 布局小案例

html

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>JS Bin</title>

</head>
<body>
<header>
  <div class="logo">
    <img src="https://static.xiedaimala.com/xdml/cdn/assets/white-logo-1a762b425df663fbccee710fe08d66951cea2fbc0a0350f03446ab30462e739f.png" alt="">
  </div>
  <ul>
    <li>首页</li>
    <li>课程</li>
    <li>优惠</li>
    <li>关于</li>
  </ul>
</header>
  <div class="content">
    <aside></aside>
    <main></main>
    <div class="ad">

    </div>
  </div>
  <div class="imglist">
    <div class="inner">
       <div class="img"></div>
    <div class="img"></div>
    <div class="img"></div>
    <div class="img"></div>
    <div class="img"></div>
    <div class="img"></div>
    <div class="img"></div>
    </div>

  </div>
</body>
</html>
```

css

```
* {
        padding: 0px;
        margin: 0px;
        box-sizing: border-box;
      }

ul{
  display:flex;
  list-style: none;
}
.logo{

  padding:5px 0px 0px 0px;

}

ul>li{

  padding:5px
}


.logo>img{
  height:30px;
}
header{
  background: #666;
  display:flex;
  justify-content:space-between;
}
.content{
  margin-top:10px;
  display: flex;
  width:800px;
  margin-left:auto;
  margin-right:auto;
}

aside{
  width:200px;
  background: #888;
}
main{
  height:400px;
  flex-grow:1;
  background: #000;
}
.ad{
  width:100px;
  background: #999;
}

.imglist{

  width:800px;
  margin-left:auto;
  margin-right:auto;
  margin-top:10px;

}
.imglist>.inner{
  display:flex;
  flex-wrap:wrap;
  margin-right:-12px;
}

.imglist>.inner>.img{
  height:191px;
  width:191px;
  background: #678;
  border:1px solid red;
  margin-right:12px;
}

```

# grid 布局

## 二维布局使用 grid，现在兼容的不多

常用属性

```
container中有
grid-template-columns;
grid-template-rows;
grid-gap;
item中的设置为
grid-column-start;
grid-column-end;
grid-row-start;
grid-row-end;

```

## grid 的小案例

html

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>JS Bin</title>
</head>
<body>
  <div class="container">
    <div class="image big"></div>
    <div class="image small"></div>
    <div class="image small"></div>
    <div class="image small"></div>
    <div class="image mid"></div>
    <div class="image mid"></div>
    <div class="image mid"></div>
    </div>
</body>
</html>
```

css

```
*{
  margin:0px;
  padding:0px;
  box-sizing:border-box;
}
.container{

  display:grid;
  grid-template-rows:240px 120px 120px 120px 120px;
  grid-template-columns:250px 250px;

  grid-template-areas:
    "big mid1"
    "big mid2"
    "small1 mid2"
    "small2 mid3"
    "small3 mid3"

}

.container>*{
  border:1px solid red;
}

.container>.image:first-child{
  grid-area:big;

}

.container>.image:nth-child(2){
  grid-area:small1;
}

.container>.image:nth-child(3){
  grid-area:small2;
}
.container>.image:nth-child(4){
  grid-area:small3;
}
.container>.image:nth-child(5){
  grid-area:mid1;
}
.container>.image:nth-child(6){
  grid-area:mid2;
}
.container>.image:nth-child(7){
  grid-area:mid3;
}

```
