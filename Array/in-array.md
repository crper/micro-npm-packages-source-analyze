# in-array

> Return true if a value exists in an array. Faster than using indexOf and won't blow up on null values.


```javascript


/*!
 * in-array <https://github.com/jonschlinkert/in-array>
 *
 * Copyright (c) 2014 Jon Schlinkert, contributors.
 * Licensed under the MIT License
 */

'use strict';

module.exports = function inArray (arr, val) {
  // 若是外部arr 不存在则使用空数组
  arr = arr || [];

  // 数组长度缓存和下标声明
  var len = arr.length;
  var i;

  // 遍历查找
  for (i = 0; i < len; i++) {
    if (arr[i] === val) {
      return true;
    }
  }
  return false;
};

```

!> 我感觉我的智商给碾压了,只是单纯的考虑了一些基础数据类型的比较和遍历
