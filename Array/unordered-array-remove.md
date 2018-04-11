# unordered-array-remove

> Efficiently remove an element from an unordered array without doing a splice

> npm : [unordered-array-remove - npm](https://www.npmjs.com/package/unordered-array-remove)


```javascript

module.exports = remove

function remove (arr, i) {
  // 若是寻找的下表位等于数据长度或者下标为负数则返回未找到
  if (i >= arr.length || i < 0) return

  // 缓存数组的最后一个元素,切割出来
  var last = arr.pop()
  if (i < arr.length) {
    // 用一个临时变量缓存被查询下标的值
    // 然后替换该值为被缓存的最后一个书
    // 最后返回给找到的值
    var tmp = arr[i]
    arr[i] = last
    return tmp
  }
  // 返回被操作后的数组
  return last
}


```
