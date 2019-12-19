---
title: "MVC浅析"
date: 2019-12-19T14:30:52+08:00
draft: false
---

## MVC浅析
### 一、MVC的三个对象
- M：Model数据模式，负责操作所有数据
     
- V：View视图，负责所有UI界面
     
- C：Controller，控制器负责其他

代码示例
```
import './app1.css'
import $ from 'jquery'

const eventBus = $(window)
// 数据相关都放到m
const m = {
  data: {
    n: parseInt(localStorage.getItem('n'))
  },
  create() {},
  delete() {},
  update(data) {
    Object.assign(m.data, data)
    eventBus.trigger('m:updated')
    localStorage.setItem('n', m.data.n)
  },
  get() {}
}
// 视图相关都放到v
const v = {
  el: null,
  html: `
  <div>
    <div class="output">
      <span id="number">{{n}}</span>
    </div>
    <div class="actions">
      <button id="add1">+1</button>
      <button id="minus1">-1</button>
      <button id="mul2">*2</button>
      <button id="divide2">÷2</button>
    </div>
  </div>
`,
  init(container) {
    v.el = $(container)
  },
  render(n) {
    if (v.el.children.length !== 0) v.el.empty()
    $(v.html.replace('{{n}}', n))
      .appendTo(v.el)
  }
}
// 其他都c
const c = {
  init(container) {
    v.init(container)
    v.render(m.data.n) // view = render(data)
    c.autoBindEvents()
    eventBus.on('m:updated', () => {
      console.log('here')
      v.render(m.data.n)
    })
  },
  events: {
    'click #add1': 'add',
    'click #minus1': 'minus',
    'click #mul2': 'mul',
    'click #divide2': 'div',
  },
  add() {
    m.update({n: m.data.n + 1})
  },
  minus() {
    m.update({n: m.data.n - 1})
  },
  mul() {
    m.update({n: m.data.n * 2})
  },
  div() {
    m.update({n: m.data.n / 2})
  },
  autoBindEvents() {
    for (let key in c.events) {
      const value = c[c.events[key]]
      const spaceIndex = key.indexOf(' ')
      const part1 = key.slice(0, spaceIndex)
      const part2 = key.slice(spaceIndex + 1)
      v.el.on(part1, part2, value)
    }
  }
}

export default c

```
### 二、EventBus
可以进行组件之间的监听和通信
- EventBus.on（）监听事件
```
eventBus.trigger('m:updated')
```
- EventBus.trigger（）触发事件
```
eventBus.on('m:updated',()=>{
     v.render(m.data.n)
 })
```
### 三、表驱动编程
- 表驱动编程是指从表里面查找信息, 将重复的代码用哈希表的方式去简化

### 四、模块化
- 模块化就是把不同的功能模块独立，是代码简洁明了




