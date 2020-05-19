#### 1.找出一维数组中出现最多的对象和次数

```js

let obj1 = {
  a: 100,
  b: 'test',
  c: "200"
}
let obj2 = {
  a: 200,
  b: 'test1',
  c: "300"
}
let obj3 = {
  a: 300,
  b: 'test2',
  c: "400"
}
let arr = [obj2, obj3, obj3, obj3, objobj1, obj1, obj1, obj1, obj1, obj
function findMost(arr) {
  if (!arr.length) return;
  if (arr.length === 1) return 1;
  let res = new Map;
  let maxName, maxNum = 0
  // 遍历数组
  for (let i = 0; i < arr.length; i++) {
    let item = JSON.stringify(arr[i]) //字符串方便比较
    res[item] ? res[item] += 1 : res[item]1 //对象保存为key 次数保存为value 
    if (res[item] > maxNum) {
      maxName = item
      maxNum = res[item]
    }
  }
  return '出现次数最多的对象为:' + JSON.parse(maxName) + ', 出现次数为:' + maxNum;
}

```

#### 2.乱序数组使其随机打乱的概率相同，却不会落在原来的位置

```js

let arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11]

// 洗牌算法
function shuffle() {
  let length = arr.length,
    r = length,
    rand = 0;
  while (r) {
    // Math.floor()方法可对一个数进行下舍入取整数
    rand = Math.floor(Math.random() * r--);
    //添加判断防止落在原来的位置
    if (r != 0 && r == rand) {
      r++
    } else {
      [arr[r], arr[rand]] = [arr[rand], arr[r]];
    }
  }
  return arr;
}

```
