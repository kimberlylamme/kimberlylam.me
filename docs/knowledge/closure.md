---
title: 闭包
last_update:
  date: 2022-10-12
---

## 闭包是什么

闭包是可以在一个内层函数中访问到其外层函数的作用域

```javascript
function init(){
	const name = "Kimberly";
  function dispalyName(){ //dispalyName()是一个闭包函数
    console.log(name);
  }
  dispalyName();
}
init();
```

## 使用场景

- 创建私有变量
- 延长变量的生命周期

:::note

一般函数的词法环境在函数返回后就被销毁，但是闭包会保存对创建时所在的词法环境的引用即便创建时所在的执行上下文被销毁，但创建时所在的词法环境依然存在，以达到延长变量的生命周期的目的

:::

```javascript
var makeCounter = function() {
  var privateCounter = 0;
  function changeBy(val) {
    privateCounter += val;
  }
  return {
    increment: function() {
      changeBy(1);
    },
    decrement: function() {
      changeBy(-1);
    },
    value: function() {
      return privateCounter;
    }
  }
};

var Counter1 = makeCounter();
var Counter2 = makeCounter();
console.log(Counter1.value()); /* logs 0 */
Counter1.increment();
Counter1.increment();
console.log(Counter1.value()); /* logs 2 */
Counter1.decrement();
console.log(Counter1.value()); /* logs 1 */
console.log(Counter2.value()); /* logs 0 */
```



:::tip

闭包在处理速度和内存消耗方面对脚本性能具有负面影响

:::