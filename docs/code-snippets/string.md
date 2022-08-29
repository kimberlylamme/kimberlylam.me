---
title: 字符串
last_update:
  date: 2022-08-12
---



## 增

[concat()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/concat) 将一个或多个字符串与原字符串合并成一个新的字符串

```javascript
const str = 'hello ';
const newStr = str.concat('world');
console.log(newStr); // 'hello world'
```

## 删

[slice()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/slice) 接收两个参数，分别是开始索引位置、结束索引位置，返回被截取的新字符串

```javascript
const str = 'My name is Lucy';
const newStr = str.slice(3,9);
console.log(newStr); // 'name i'
```

[substring()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/substring) 接收两个参数，分别是需要截取第一个字符的索引、结束截取字符的索引（空则截取到末尾），返回被截取的新字符串

```javascript
const str = 'My name is Lucy';
const newStr = str.substring(3,9);
console.log(newStr); // 'name i'
```

## 改

[trim()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/Trim) 删除字符串开头和结束两端的空白符

 [trimStart()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/trimStart) 删除字符串开头的空白符

 [trimEnd()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/trimEnd) 删除字符串末端的空白符

```javascript
const str = ' hello world ';
const newStr = str.trim();
console.log(newStr); // 'hello world'
```

[repeat()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/repeat) 接收一个数字，返回一个指定数量的重复字符串

```javascript
const str = 'abc';
const newStr = str.repeat(3);
console.log(newStr); // 'abcabcabc'
```

[padStart()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/padStart) 接收2个参数，分别为当前字符串需要填充到的目标长度、需要填充的字符串，返回在原字符串开头填充字符串直到目标长度所形成的新字符串

[padEnd()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/padEnd) 接收2个参数，分别为当前字符串需要填充到的目标长度、需要填充的字符串，返回在原字符串末尾填充指定的填充字符串直到目标长度所形成的新字符串

```javascript
const str = 'abc';
const startStr = str.padStart('5','hi');
console.log(startStr); // 'hiabc'
const endStr = str.padEnd('5','hi');
console.log(endStr); // 'abchi'
```

[toLowerCase()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase) 将字符串全部转换为小写字符串

[toUpperCase()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/toUpperCase) 将字符串全部转换为大写字符串

```javascript
const str = 'Abc';
const newStr = str.toLowerCase();
console.log(newStr); // 'abc'
const upStr = str.toUpperCase();
console.log(upStr); // 'ABC'
```

## 查

[charAt()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/charAt) 接收一个索引参数，返回指定的字符串

```javascript
const str = 'abc';
const newStr = str.charAt(1);
console.log(newStr); // 'b'
```

[indexOf()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf) 接收2个参数，分别为要查找的字符串值、开始查找的位置，返回第一次出现值的索引，如果找不到，则返回 `-1`

```javascript
const str = 'abc';
const a = str.indexOf('a');
const b = str.indexOf('d');
console.log(a); // 0
console.log(b); // -1
```

[startsWith()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/startsWith) 接收2个参数，分别为要搜索的字符串、开始搜索的位置，如果在开头找到了给定的字符则返回 `true`,否则返回 `false`

[endsWith()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/endsWith) 接收2个参数，分别为要搜索的字符串、截取字符串的总长度，如果在末尾找到了给定的字符则返回 `true`,否则返回 `false`

```javascript
const str = 'my name is lucy';
console.log(str.startsWith('my')) // true
console.log(str.startsWith('name')) // false
console.log(str.startsWith('name',3)) // true
console.log(str.endsWith('lucy')) // true
console.log(str.endsWith('is')) // false
console.log(str.endsWith('is',10)) // true
```

[includes()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/includes) 接收2个参数，分别为要搜索的字符串、开始搜索的位置，如果字符串包含搜索字符串，返回 `true`,否则返回 `false`

```javascript
const str = 'my name is lucy';
console.log(str.includes('my')); // true
console.log(str.includes('my',1)); // false
```

## 转换方法

[split()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/split) 接收2个参数，分别为一个字符串或者正则表达式、限定返回的分割片段数量，返回原字符串以分隔符出现位置分隔而成的一个数组

```javascript
const str = 'my name is lucy';
const arr = str.split(' ');
console.log(arr); // ['my', 'name', 'is', 'lucy']
```

[btoa()](https://developer.mozilla.org/zh-CN/docs/Web/API/btoa) `Base64`编码

[atob()](https://developer.mozilla.org/zh-CN/docs/Web/API/atob) `Base64`解码

```javascript
const str = 'abc';
const a = btoa(str);
console.log(a); // 'YWJj'
const b = atob(a);
console.log(b); // 'abc'
```

[encodeURIComponent()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent) `ASCII`码编码

[decodeURIComponent()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/decodeURIComponent) `ASCII`码解码

```javascript
const str = '你好';
const a = encodeURIComponent(str);
console.log(a); // '%E4%BD%A0%E5%A5%BD'
console.log(decodeURIComponent(a)); // '你好'
```

## 模板匹配

[replace()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/replace) 接收2个参数，分别为正则或者要替换的字符串、需要替换的字符串，符合条件的则替换第一个，返回新的字符串

[replaceAll()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/replaceAll) 接收2个参数，分别为正则或者要替换的字符串、需要替换的字符串，符合条件的则全部替换，返回新的字符串

```javascript
const str = 'my name is lucy,my classmate is mike';
const a = str.replace('is','iss');
console.log(a); // 'my name iss lucy,my classmate is mike'
const b = str.replaceAll('is','iss');
console.log(b); // 'my name iss join,my classmate iss mike'
```

[match()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/match) 传入一个正则作为参数，检索返回一个字符串匹配正则表达式的结果

```javascript
const str = 'My name is Lucy';
const regex = /[A-Z]/g;
const res = str.match(regex);
console.log(res); //['M','L']
```

[search()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/search) 传入一个正则作为参数，如果匹配成功，则返回正则表达式在字符串中首次匹配的索引，否则返回 `-1`

```javascript
const str = 'My name is Lucy';
const regex = /[A-Z]/g;
const res = str.search(regex);
console.log(res); //0
```



