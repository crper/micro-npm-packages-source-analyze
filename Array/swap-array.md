# swap-array

> Swap position of two items in array without changing the state of the passed array.


> npm : [swap-array - npm](https://www.npmjs.com/package/swap-array)


```javascript

export default (Arr, Caller, Target) => {
  // 数组的实例, 缓存传入的 arr
  let Instance = Arr.constructor();
  let Stash = Arr;

  // 判断传入 arr 的类型
  let InstanceType = Array.isArray(Instance) ? 'array' : typeof Instance;

  // 如果不是数组则抛出异常
  // Check types and throw err if no arr is passed
  if(InstanceType !== 'array') throw '[ERR] SwapArray expects a array as first param';

  // Copy the Arr-Content into new Instance - so we don't overwrite the passed array
  // 遍历复制传入的 arr,避免直接操作传入的 arr
  Stash.map((s, i) => Instance[i] = s);

  // Update indexes
  // 更新索引
  // 这个也不难理解.可以这样拆解
  // splice 切割对应下标的,并将切割出来的值,赋值到 caller 的位置
  Instance[Caller] = Instance.splice(Target, 1, Instance[Caller])[0];

  // 返回交换后的数组
  return Instance;
}


```
