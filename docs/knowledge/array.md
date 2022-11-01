---
title: 数组
last_update:
  date: 2022-08-11
---

## 增

[push()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/push) 接收任意数量的参数并将他们添加到数组末尾，返回新数组长度，对原数组有改变

```javascript
let arr = ['0'];
let count = arr.push('1','2');
console.log(count); // 3
console.log(arr); // ['0','1','2']
```

[unshift()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift) 在数组开头添加任意数量的参数，返回新数组长度，对原数组有改变

```javascript
let arr = ['0'];
let count = arr.unshift('1','2');
console.log(count) // 3
console.log(arr) // ['1','2','0']
```

  [splice()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/splice) 传入三个参数，分别是开始位置、`0`（要删除的元素数量）、插入元素，返回空数组，对原数组有改变

```javascript
let arr = ['1','2'];
let newArr = arr.splice(1,0,'3','4');
console.log(arr); // ['1','3','4','2']
console.log(newArr); // []
```

[concat()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/concat) 合并两个或多个数组，返回新数组，对原数组无改变

```javascript
let arr = ['1','2'];
let newArr = arr.concat('3',['4','5']);
console.log(arr); // ['1','2']
console.log(newArr); // ['1','2','3','4','5']
```

## 删

[pop()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/pop) 删除数组的最后一项，改变数组的长度，返回被删除的项，对原数组有改变

```javascript
let arr = ['1','2','3'];
let newString = arr.pop();
console.log(arr); // ['1','2']
console.log(newString); // 3
```

[shift()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/shift) 删除数组的第一项，改变数组的长度，返回被删除的项，对原数组有改变

```
let arr = ['1','2','3'];
let newString = arr.shift();
console.log(arr); // ['2','3']
console.log(newString); // 1
```

[splice()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/splice) 传入两个参数，分别是开始位置、删除元素的数量，返回删除元素的数组，对原数组有改变

```javascript
let arr = ['1','2','3'];
let newArr = arr.splice(0,1);
console.log(arr) // ['2','3']
console.log(newArr) // ['1']
```

[slice()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/slice) 传入两个参数，分别是开始位置、结束位置（为空则默认最后位置），返回被截取的数组，对原数组无改变

```javascript
let arr = ['1','2','3','4','5'];
let newArr = arr.slice(1,3);
console.log(arr); // ['1','2','3','4','5']
console.log(newArr); // ['2','3']
```

## 查

[indexOf()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf) 返回数组要查找元素在数组中的索引，没找到则返回 `-1`

```javascript
const arr = ['1','2','3'];
console.log(arr.indexOf('1')); // 0
console.log(arr.indexOf('4')); // -1
```

[includes()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/includes) 判断数组是否包含一个指定的值，包含则返回 `true`,不包含返回 `false`

```javascript
const arr = ['1','2','3'];
console.log(arr.includes('1')); // true
console.log(arr.includes('4')); // false
```

[find()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/find) 返回第一个匹配的元素

```javascript
const arr = [1, 2, 3, 4, 5];
const res = arr.find((item) => item > 2)
console.log(res) // 3
```

## 排序方法

[reverse()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse) 将数组元素方向反转，并返回该数组，对原数组有改变

```javascript
const arr = [1, 2, 3, 4, 5];
const res = arr.reverse();
console.log(res); // [5,4,3,2,1]
```

[sort()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/sort) 接收一个比较函数，用于判断哪个值应该排序在前面；`a>b` 升序、 `a<b` 降序

```javascript
const arr = [{'id':1,'value':1},{'id':2,'value':9},{'id':3,'value':2}];
const compare = (a,b) =>{
    if(a.value > b.value){
	 	return 1
	}else{
		return -1
	}
}
arr.sort(compare)
console.log(arr); // [{'id':1,'value':1},{'id':3,'value':2},{'id':2,'value':9}];
```

## 迭代方法

[map()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/map) 对数组每一项都运行传入的函数，返回由每次函数调用的结构构成的数组

```javascript
const arr = [1,2,3];
const newArr = arr.map((item,key,curArr)=> {
	return item * 2;
})
console.log(arr); // [1,2,3]
console.log(newArr); // [2, 4, 6]
```

[forEach()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) 对数组每一项都运行传入的函数，没有返回值，对原数组有改变

```javascript
const arr = [1,2,3];
arr.forEach((item,key,curArr)=> item * 2)
console.log(arr); // [1,2,3]
```

[filter()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/filter) 对数组每一项都运行传入的函数，返回过滤后的新数组，对原数组有改变

```javascript
const arr = [1,2,3,4,5];
const newArr = arr.filter((item,key,curArr) => {
	if(item > 2) return true;
})
console.log(arr); // [1,2,3,4,5]
console.log(newArr); // [3,4,5]
```

[some()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/some) 对数组每一项都运行传入的函数，如果至少有一个元素返回 `true`，则这个方法返回 `false`

```javascript
const arr = [1,2,3,4,5];
const res = arr.some((item,key,curArr)=>{
	return item === 2;
})
console.log(res) // true
```

[every()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/every) 对数组每一项都运行传入的函数，如果所有元素都返回 `true`，则这个方法返回 `false`

```javascript
const arr = [1,2,3,4,5];
const res = arr.every((item,key,curArr)=>{
	return item > 0;
})
console.log(res) // true
```

[reduce()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce) 传入2个参数，分别是 `callbackFn` 和默认上一次返回值的初始值，`callbackFn`可传入四个参数，分别是上一次调用 `callbackFn` 时返回的值、当前值，当前索引，遍历的数组，最后返回的是使用 “reducer” 回调函数遍历整个数组后的结果

```javascript
const arr = [1,2,3,4,5];
const init = 0;
const sum = arr.reduce((pre,cur,key,curArr)=>{
	return pre + cur
},init);
console.log(sum); // 15
```

## 转换方法

[join()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/join) 接收一个参数，即字符串分隔符，返回包含所有项的字符串

```javascript
const arr = ['h','e','l','l','o'];
const res = arr.join(',');
console.log(res); //h,e,l,l,o
```

[Array.from()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/from) 传入一个可迭代对象，返回一个新的数组

```javascript
const string = 'foo';
const arr = Array.from(string);
console.log(arr); // ['f','o','o']
```

## 数组去重

```javascript
const a = [1,3,5];
const b = [1,2,3];
const c = [...new Set([...a,...b])];
console.log(c); // [1, 3, 5, 2]
```



## 深拷贝

[JSON.parse(JSON.stringify())](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse)

```javascript
let a = [{id:{value:2}}];
let b = JSON.parse(JSON.stringify(a));
b[0].id.value = 3;
console.log(a); // [{id:{value:2}}]
console.log(b); // [{id:{value:3}}]
```

[structuredClone()](https://developer.mozilla.org/zh-CN/docs/web/api/structuredClone)

```javascript
let a = [{id:1},{id:2},{id:3}];
let b = structuredClone(a);
b[0].id = 9;
console.log(a); // [{id:1},{id:2},{id:3}]
console.log(b); // [{id:9},{id:2},{id:3}]
```

