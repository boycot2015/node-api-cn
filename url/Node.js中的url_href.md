<!--introduced_in=v0.10.0-->

> 稳定性: 2 - 稳定的

`url` 模块提供了一些实用函数，用于 URL 处理与解析。
可以通过以下方式使用：

```js
const url = require('url');
```
* {string}

获取及设置序列化的URL。

```js
const { URL } = require('url');
const myURL = new URL('https://example.org/foo');
console.log(myURL.href);
  // 输出 https://example.org/foo

myURL.href = 'https://example.com/bar';
console.log(myURL.href);
  // 输出 https://example.com/bar
```

获取`href`属性的值等同于调用[`url.toString()`][]。

将此属性的值设置为新值等同于[`new URL(value)`][`new URL()`]使用创建新的`URL`对象。`URL`对象的每个属性都将被修改。

如果给`href`属性设置的值是无效URL，将会抛出`TypeError`。


* {string}

获取及设置URL的密码(password)部分。

```js
const { URL } = require('url');
const myURL = new URL('https://abc:xyz@example.com');
console.log(myURL.password);
  // 输出 xyz

myURL.password = '123';
console.log(myURL.href);
  // 输出 https://abc:123@example.com
```

包含在赋给`password`属性的值中的无效URL字符是[百分比编码][]。请注意选择哪些字符进行百分比编码可能与[`url.parse()`][]和[`url.format()`][]方法产生的不同。
* {string}

获取及设置URL的路径(path)部分。

```js
const { URL } = require('url');
const myURL = new URL('https://example.org/abc/xyz?123');
console.log(myURL.pathname);
  // 输出 /abc/xyz

myURL.pathname = '/abcdef';
console.log(myURL.href);
  // 输出 https://example.org/abcdef?123
```

包含在赋给`pathname`属性的值中的无效URL字符是[百分比编码][]。请注意选择哪些字符进行百分比编码可能与[`url.parse()`][]和[`url.format()`][]方法产生的不同。
* {string}

获取及设置URL的序列化查询(query)部分部分。

```js
const { URL } = require('url');
const myURL = new URL('https://example.org/abc?123');
console.log(myURL.search);
  // 输出 ?123

myURL.search = 'abc=xyz';
console.log(myURL.href);
  // 输出 https://example.org/abc?abc=xyz
```

任何出现在赋给`search`属性值中的无效URL字符将被[百分比编码][]。请注意选择哪些字符进行百分比编码可能与[`url.parse()`][]和[`url.format()`][]方法产生的不同。


* {string}

获取及设置URL的协议(protocol)部分。

```js
const { URL } = require('url');
const myURL = new URL('https://example.org');
console.log(myURL.protocol);
  // 输出 https:

myURL.protocol = 'ftp';
console.log(myURL.href);
  // 输出 ftp://example.org/
```

如果给`protocol`属性设置的值是无效值，那么该值将被忽略。
