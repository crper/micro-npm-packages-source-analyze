# document-ready

> Document ready listener for modern browsers

> npm: [document-ready - npm](https://www.npmjs.com/package/document-ready)


```javascript
// 这个库主要来监听文档是否加载完毕

'use strict'

// 断言库,node 的,不用管他
var assert = require('assert')

module.exports = ready

function ready (callback) {
  // nodejs 里面没有 document,会抛出 undefined, 然后报错
  assert.notEqual(typeof document, 'undefined', 'document-ready only runs in the browser')
  // document.readyState 有三个状态
  // loading : 加载中
  // interactive: 文档已经加载完毕,可以访问 DOM 元素
  // complete: 网页加载完毕,包括样式这些

  var state = document.readyState
  if (state === 'complete' || state === 'interactive') {
    return setTimeout(callback, 0)
  }

  // DOMContentLoaded 状态是 DOM 构建完毕就执行回调函数,不等待样式和其他静态资源这些
  document.addEventListener('DOMContentLoaded', function onLoad () {
    callback()
  })
}


```
