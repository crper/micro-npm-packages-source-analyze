# is-generator

>检查一个函数是生成器还是生成器函数
> npm: [is-generator - npm](https://www.npmjs.com/package/is-generator)


```javascript

/**
 * Export generator function checks.
 */
module.exports = isGenerator
module.exports.fn = isGeneratorFunction

/**
 * Check whether an object is a generator.
 *
 * @param  {Object}  obj
 * @return {Boolean}
 */
function isGenerator (obj) {
  // 判断是否是生成器
  return obj &&
    typeof obj.next === 'function' &&
    typeof obj.throw === 'function'
}

/**
 * Check whether a function is generator.
 *
 * @param  {Function} fn
 * @return {Boolean}
 */
function isGeneratorFunction (fn) {
  return typeof fn === 'function' &&
    fn.constructor &&
    fn.constructor.name === 'GeneratorFunction'
}

```

!> 在 chrome 64 下,这个判断是否为生成器函数的方法是错误的..有可能是版本的差异,毕竟这个库写的比较早

```javascript

// 应该改成这样
function isGeneratorFunction (fn) {
  return typeof fn === 'function' &&
    fn.constructor &&
    (fn.constructor.name === 'GeneratorFunction' || fn.constructor.constructor.name === 'GeneratorFunction')
}

```
