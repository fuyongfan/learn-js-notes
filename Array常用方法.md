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
原数组不变，起始位置索引到结束位置的索引处（不含结束位置）的内容以新数组的形式返回，参数可为负数
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
console.log(ary, res); // [0, 6, 6, 6, 3, 4, 5] [1, 2]
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
