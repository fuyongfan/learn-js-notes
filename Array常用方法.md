## push
原数组改变， 返回新数组的长度  可以传多个参数
```
var ary = [1, 3];
var res = ary.push(3, 4);
console.log(ary, res); // [1, 3, 3, 4] 4
```
## pop
原数组改变，返回删除的那一项  不可传参（传了不生效）

```
var ary = [1, 3];
var res = ary.pop();
console.log(ary, res); // [1], 3
```
## shift
原数组改变，返回删除的那一项  不可传参（传了不生效）
```
var ary = [1, 3];
var res = ary.shift();
console.log(ary, res); // [3] 1
```
## unshift
原数组改变， 返回新数组的长度  可以传多个参数
```
var ary = [1, 3];
var res = ary.unshift(3, 6);
console.log(ary, res); // [3, 6, 1, 3] 4
```
## slice
原数组不变，起始位置索引到结束位置的索引处（不含结束位置）的内容以新数组的形式返回，参数可为负数 . (浅拷贝)
```
var ary = [0, 1, 2, 3, 4, 5];
var res = ary.slice(1, 3);
console.log(ary, res); // [0, 1, 2, 3, 4, 5] [1, 2]
```
## splice
原数组改变， 删除的项以数组的形式返回
```
var ary = [0, 1, 2, 3, 4, 5];
var res = ary.splice(1, 2, 1, 1, 1);
console.log(ary, res); // [0, 1, 1, 1, 3, 4, 5] [1, 2]
```
## join
原数组不变， 数组中的每一项分别调用toString方法，然后拼接起来作为返回值
## concat
原数组不变， 返回拼接之后的数组， 参数为数组时：将数组的每一项添加到末尾；非数组时：直接添加到末尾
```
var ary = [1];
var res = ary.concat(2, [3, 4]);
console.log(ary, res); // [1] [1, 2, 3, 4]
```
## 排序
1. sort
原数组改变，返回排序后的数组 a - b 小 --> 大
```
var ary = [1, 3, 28, 23];
var res = ary.sort((a, b) => a - b);
console.log(ary, res); // [1, 3, 23, 28]  [1, 3, 23, 28]
```
2. reverse
原数组改变，返回倒叙后的数组
```
var ary = [1, 3, 28, 23];
var res = ary.reverse();
console.log(ary, res); // [23, 28, 3, 1] [23, 28, 3, 1]
```
## 其他方法
1. every 数组每一项都返回true 则返回 true
```
var ary = [0, 1, 2, 3, 4, 5];
ary.every((item, index, ary) => item > 3) // false
ary.every((item, index, ary) => item > -1) // true
```
2. some 数组中其中一项返回 true 则返回 true
```
var ary = [0, 1, 2, 3, 4, 5];
ary.some((item, index, ary) => item > 3) // true
ary.some((item, index, ary) => item > 5) // false
```
3. forEach 没有返回值
```
var ary = [0, 1, 2, 3, 4, 5];
var count = 0;
ary.forEach((item, index, ary) => {
    if (item > 3) {
        count++;
    }
});
console.log(ary, count); // [0, 1, 2, 3, 4, 5] 2
```
4. map 返回每次调用的结果组成的数组
```
var ary = [0, 1, 2, 3, 4, 5];
var res = ary.map((item, index, ary) => ++item);
console.log(ary, res); // [0, 1, 2, 3, 4, 5] (6) [1, 2, 3, 4, 5, 6]
```
5. fliter 把数组中符合筛选条件的项添加到一个数组中并返回
```
var ary = [0, 1, 2, 3, 4, 5];
ary.filter((item, index, ary) => item > 3) // [4, 5]
ary.filter((item, index, ary) => item > 5) // []
```
6. findIndex 遍历每一项，其中一项符合条件，则返回该项对应的索引并结束遍历
```
var ary = [1, 2, 3, 4, 5];
var res = ary.findIndex((item, index, ary) => {
    console.log(item, index, ary);
    return item === 2;
});
console.log(ary, res);
1 0 [ 1, 2, 3, 4, 5 ]
2 1 [ 1, 2, 3, 4, 5 ]
[ 1, 2, 3, 4, 5 ] 1
```
#### 以上6个方法均不会改变原数组，并且回调中都有3个参数 ———— item, index, ary
7. reduce 和reduceRight 接受参数 ———— pre, cur, index, ary
```
var ary = [0, 1, 2, 3, 4, 5];
var res = ary.reduce((pre, cur, index, ary) => {
    console.log(index); // 1, 2, 3, 4, 5
    return pre + cur;
});
console.log(ary, res); // [0, 1, 2, 3, 4, 5] 15
```
7. indexOf lastIndexOf

## 数组中扩展方法
1. 扩展运算符
```
let ary = [1, 2, 3];
console.log(...ary);
// 1, 2, 3
```
- 可以添加表达式
```
let foo = true;
let ary = [
    ...(foo ? [1, 2, 3] : [])
];
console.log(ary); // [1, 2, 3]
```
- 复制数组
```
let arr1 = [1, 2, 3];
let arr2 = [...arr1];
let [...arr2] = arr1;
arr2[0] = 12;
console.log(arr1, arr2); // [ 1, 2, 3 ] [ 12, 2, 3 ]
```
- 拼接数组
```
let arr1 = [1, 2, 3];
let arr2 = [4, 5, 6];
let arr3 = [...arr1, ...arr2];
console.log(arr3); // [ 1, 2, 3, 4, 5, 6 ]
```
- 将字符串转换成数组
```
let str = 'hello';
let arr = [...str];
console.log(arr); // [ 'h', 'e', 'l', 'l', 'o' ]
```
- 实现了 Iterator 接口的对象
```
let nodeList = document.querySelectorAll('div');
let array = [...nodeList];
```

2. Array.from
```
let arrayLike = {
    '0': 'a',
    '1': 'b',
    '2': 'c',
    length: 3
};

// ES5的写法
var arr1 = [].slice.call(arrayLike); // ['a', 'b', 'c']

// ES6的写法
let arr2 = Array.from(arrayLike); // ['a', 'b', 'c']
```
- Array.from, 可以接收第二个参数， 类似于 Array.from(arrLike).map();
```
let arrLike = {
    0: 0,
    1: 1,
    2: 2,
    length: 3
};
let arr = Array.from(arrLike, item => item + 1);
console.log(arr); // [ 1, 2, 3 ]
```
3. Array.of 
```
Array.of(); // []
Array.of(undefined); // [undefined]
Array.of(1, 2); // [1, 2]
```
4. Array.copyWithin(target, start, end);
5. Array.find();  与 filter 区别
```
let arr = [1, 2, 3, 4, 5];

let res = arr.filter(item => item === 3);

console.log(res); // [3]
```
```
let arr = [1, 2, 3, 4, 5];

let res = arr.find(item => item === 3);

console.log(res); // 3
```
- find 找到第一个则停止查找， 没找到返回 undefined
- findIndex 找到第一个则停止查找， 没找到返回 -1
- find 和 findIndex 接收第二个参数， 绑定回调函数 this 指向

```
function f(v){
  return v > this.age;
}
let person = {name: 'John', age: 20};
[10, 12, 26, 15].find(f, person);    // 26
```
- 另外，这两个方法都可以发现NaN，弥补了数组的indexOf方法的不足。
```
[NaN].indexOf(NaN)
// -1

[NaN].findIndex(y => Object.is(NaN, y))
// 0
```
6. Array.fill()
```
let arr = [1, 2, 3, 4, 5];
arr.fill('hello', 0, 2);
console.log(arr); // [ 'hello', 'hello', 3, 4, 5 ]
```
7. keys() values() entries()
```
let arr = [1, 2, 3];
for (let key of arr.keys()) {
    console.log(key);
} // 0, 1, 2
```
8. Array.includes();
```
let arr = [1, 2, 3, NaN];
console.log(arr.includes(NaN)); // true
```
