---
title: 原型链
last_update:
  date: 2022-08-10
---

## 原型链是什么

JavaScript只有一种结构：对象。每个实例对象都有一个私有属性（\_\_proto\_\_）指向它的构造函数的原型对象（__prototype__）。该原型对象也有一个自己的原型对象（\_\_proto\_\_），层层向上到一个对象的原型对象为`null`。根据定义，`null`没有原型，并作为这个原型链中的最后一个环节

## 继承属性

JavaScript对象有一个指向一个原型对象的链。当试图访问一个对象的属性时，它不仅仅在该对象上搜寻，还会搜寻该对象的原型，以及该对象的原型的原型，以此层层向上搜索，直到找到一个名字匹配的属性或到达原型链的末尾

```javascript
function doSomething(){}
doSomething.prototype.foo = "bar";
var doSomeInstancing = new doSomething();
doSomeInstancing.prop = "some value";
console.log("doSomeInstancing.prop:      " + doSomeInstancing.prop);
console.log("doSomeInstancing.foo:       " + doSomeInstancing.foo);
console.log("doSomething.prop:           " + doSomething.prop);
console.log("doSomething.foo:            " + doSomething.foo);
console.log("doSomething.prototype.prop: " + doSomething.prototype.prop);
console.log("doSomething.prototype.foo:  " + doSomething.prototype.foo);

//运行结果
doSomeInstancing.prop:      some value
doSomeInstancing.foo:       bar
doSomething.prop:           undefined
doSomething.foo:            undefined
doSomething.prototype.prop: undefined
doSomething.prototype.foo:  bar
```

:::note

如果属性不存在 `doSomeInstancing` 的 `__proto__` 的 `__proto__` 中，那么就会在`doSomeInstancing` 的 `__proto__` 的 `__proto__` 的 `__proto__` 中查找。然而，这里存在个问题：`doSomeInstancing` 的 `__proto__` 的 `__proto__` 的 `__proto__` 其实不存在。因此，只有这样，在 `__proto__` 的整个原型链被查看之后，这里没有更多的 `__proto__` ，浏览器断言该属性不存在，并给出属性值为 `undefined` 的结论。

:::