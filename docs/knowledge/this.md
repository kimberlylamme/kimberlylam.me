---
title: this关键字
last_update:
  date: 2022-08-13
---

## 使用场合

### 1、全局环境

全局环境使用 `this`，它指的就是顶层对象`window`

```javascript
this === window //true
function f(){
	console.log(this === window)
}
f() //true
```

### 2、构造函数

构造函数中的`this`，指的是实例对象

```javascript
const Obj = function (p){
	this.p = p;
}
const o = new Obj('kimberly')
o.p //'kimberly'
```

### 3、对象的方法

（1）调用方法时，请在对象环境中调用，而不是在全局环境中调用

（2）`this`在顶级对象中，只在第一层方法内有效，在多层方法内无法指向顶级对象

```javascript
//案例1
const obj = {
    foo:function(){
        console.log(this)
    }
}
obj.foo() //obj
//情况1
(obj.foo = obj.foo)() //window
//情况2
(false || obj.foo)() //window
//情况3
(1,obj.foo)() //window

//案例2
const a = {
    p:'Hello',
    b:{
        m:function(){
          console.log(this.p)
          console.log(this.o)
        },
        o:"world"
    }
}
a.b.m() //undefined 'world'
```

## 绑定this的方法

### 1、Function.prototype.call()

可以指定函数内部`this`的指向，与apply方法类似

```javascript
func.call(obj, arg1, arg2, ...)
```

### 2、Function.prototype.apply()

可以指定函数内部`this`的指向，与call方法类似

```javascript
func.apply(obj, [arg1, arg2, ...])
```

### 3、Function.prototype.bind()

`bind()`方法用于函数体内的`this`绑定到某个对象，然后返回一个新对象

```javascript
var counter = {
  count: 0,
  inc: function () {
    this.count++;
  }
};
var obj = {
  count: 100
};
var func = counter.inc.bind(obj);
func();
obj.count // 101
```

