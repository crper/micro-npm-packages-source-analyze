# is-sorted

>A small module to check if an Array is sorted.

> 这个库专门用来判断数组是否已经排序的

> npm :[is-sorted - npm](https://www.npmjs.com/package/is-sorted)

- 官方源码

```javascript

// 默认升序
function defaultComparator (a, b) {
  return a - b
}

module.exports = function checksort (array, comparator) {
  // 比较函数,没有传入则默认调用升序比较函数
  comparator = comparator || defaultComparator

  // 若是遍历找到比较值大于0的,就证明顺序不对,返回 false
  for (var i = 1, length = array.length; i < length; ++i) {
    if (comparator(array[i - 1], array[i]) > 0) return false
  }

  return true
}

```
