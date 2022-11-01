---
title: 本地存储
last_update:
  date: 2022-10-13
---

## cookie

- `cookie`的数据会自动的传递到服务器，服务器端也可以写`cookie`到客户端
- 大小：不超过4KB

```javascript
document.cookie ="name=kimberly; domain=kimberly.me;path=/;Max-Age=604800"
```

## localStorage

- 生命周期：持久化的本地存储，除非主动删除数据，否则数据永远不会过期
- 存储的信息在同一域名中是共享的
- 当本页操作（增、删、改）了`localStorage`的时候，本页面不会触发`storage`事件，但是别的页面会触发`storage`事件

- 大小：约5M（跟浏览器厂商有关）
- `localStorage`本质上是对字符串的读取，如果存储内容多的话会消耗内存空间，会导致页面变卡
- 受同源策略的限制
- 无法设置过期时间
- 只能存入字符串，不能存入对象

```javascript
localStorage.setItem('username','kimberly')
localStorage.getItem('username')
localStorage.removeItem('username')
localStorage.clear() //一次性清除
```

## sessionStorage

`sessionStorage`和 `localStorage`使用方法基本一致，唯一不同的是生命周期，一旦页面（会话）关闭，`sessionStorage` 将会删除数据

## indexDB

- 储存量没有上限
- 所有操作都是异步
- 原生支持存储`JS`的对象
