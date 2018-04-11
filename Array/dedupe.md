# dedupe

> removes duplicates from your array.

> npm : [dedupe - npm](https://www.npmjs.com/package/dedupe)

```javascript

'use strict'

function dedupe (client, hasher) {
    // 给 hasher 一个默认值
    hasher = hasher || JSON.stringify

    // 声明两个变量,一个储存唯一数据,一个缓存标识
    const clone = []
    const lookup = {}

    // 遍历数组
    for (let i = 0; i < client.length; i++) {
        // 定义一个变量缓存当前遍历的值
        let elem = client[i]
        // 缓存该实例的处理的结果
        let hashed = hasher(elem)
        // 若是没有标识位的代表还没有重复数据,推入到数组中,
        // 然后给该数据设置标识位代表已经有了一个
        if (!lookup[hashed]) {
            clone.push(elem)
            lookup[hashed] = true
        }
    }

    return clone
}

module.exports = dedupe

```
