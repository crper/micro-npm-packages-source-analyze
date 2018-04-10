# is-number

> Returns true if the value is a number. comprehensive tests.

> url :[is-number - npm](https://www.npmjs.com/package/is-number)

```javascript
/*!
 * is-number <https://github.com/jonschlinkert/is-number>
 *
 * Copyright (c) 2014-2018, Jon Schlinkert.
 * Released under the MIT License.
 */

'use strict';

module.exports = function isNumber(num) {
  var number = +num; // 隐形转换,若是可以会转为数字类型;

  // 排除 NAN 和 无穷数,直接返回 false
  if (number - number !== 0) {
    // Discard Infinity and NaN
    return false;
  }

  // 转换的值和传入值的全等比较!!!
  if (number === num) {
    return true;
  }

  if (typeof num === 'string') {
    // String parsed, both a non-empty whitespace string and an empty string
    // will have been coerced to 0. If 0 trim the string and see if its empty.
    // 若弱隐形转换为0 且传入字符串为空的,肯定不是数字
    if (number === 0 && num.trim() === '') {
      return false;
    }
    // 否则便是数字
    return true;
  }

  // 其他情况一律返回 false
  return false;
};
```
