#### 1.找出一维数组中出现最多的对象和次数

```js

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

#### 3.判断一个数是否是素数(质数)

```js

function primeNumber(num) {
  let count = 0; //因子和
  for (var i = 1; i <= num; i++) {
    if (num % i == 0) { //因子
      count++;
    }

  if (count == 2) {
    console.warn(num + "是素数");
  } else {
    console.warn(num + "不是素数");
  }
}

```

#### 4.JS写斐波那契数列

```js

//  方法1：递归
function fb1(n) {
  if (n <= 2) {
    return 1;
  } else {
    return fb1(n - 1) + fb1(n - 2);
  }
}
// 方法1的递归方法基础上进行尾调用优化：
function fb2(n, res1 = 1, res2 = 1) {
  if (n <= 2) {
    return res2;
  } else {
    return fb2(n - 1, res2, res1 + res2);
  }
}

```

#### 5.JS数组去重

```js

 //不包括对象,对象去重需要先转String
function distinct(arr) { 
  let newArr = []
  for (let i = 0; i < arr.length; i++) {
    if (!newArr.includes(arr[i])) {
      newArr.push(arr[i])
    }
  }
  return newArr

// es6数组去重
function distinct2(arr) {
  let newArr = [...new Set(arr)]
  return newArr
}

```






