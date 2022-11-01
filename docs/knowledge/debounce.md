---
title: 防抖与节流
last_update:
  date: 2022-10-12
---

## 防抖(debounce)

N秒后在执行该事件，若在N秒内被重复触发，则重新计时

```javascript
function debounce(func,wait,immediate){
  let timeout;
  return function(){
    let that = this;
    let args = arguments;
    if(timeout) clearTimeout(timeout);
    if(immediate){
      let callNow = !timeout
      timeout = setTimeout(function(){
        timeout = null;
      },wait);
      if(callNow) func.apply(that,args)
    }else{
      timeout = setTimeout(function(){
        func.apply(that,args)
      },wait);
    }
  }
}
```

应用场景：

- 搜索框搜索输入，只需用户最后一次输完，再发送请求
- 手机号、邮箱的验证输入检测
- 窗口的大小调整，只需窗口调整完后，计算窗口大小，防止重复渲染

## 节流(throttle)

N秒内只运行一次，若在N秒内重复触发，只有一次生效

```javascript
function throttled(fn,delay){
  let timer = null;
  let startTime = Date.now();
  return function (){
    let curTime = Date.now();
    let remaining = delay - (curTime - startTime)
    let that = this
    let args = arguments
    clearTimeout(timer)
    if(remaining <= 0){
      fn.apply(that,args)
      startTime = Date.now()
    }else{
      timer = setTimeout(fn,remaining)
    }
  }
}
```

应用场景：

- 滚动加载，加载更多或滚到底部监听
- 搜索框，搜索联想功能
