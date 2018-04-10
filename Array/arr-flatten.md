# arr-flatten

> Recursively flatten an array or arrays. This is the fastest implementation of array flatten. https://github.com/jonschlinkert

> npm : [arr-flatten - npm](https://www.npmjs.com/package/arr-flatten)


```javascript


/*!
 * arr-flatten <https://github.com/jonschlinkert/arr-flatten>
 *
 * Copyright (c) 2014-2017, Jon Schlinkert.
 * Released under the MIT License.
 */

'use strict';

// 这个采用递归的思路实现的
module.exports = function (arr) {
  // 传入空数组的作用是来缓存拍平的数据
  return flat(arr, []);
};

function flat(arr, res) {
  // 声明下标和临时变量 cur,以及缓存数组长度
  var i = 0, cur;
  var len = arr.length;
  for (; i < len; i++) {
    // 取得当前循环的值
    cur = arr[i];
    // 若是判断为数组则递归调用自身再执行,到执行完毕
    Array.isArray(cur) ? flat(cur, res) : res.push(cur);
  }
  // 返回拍平的数组
  return res;
}

```
