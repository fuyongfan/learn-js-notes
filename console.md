# console 常用方法
1. console.log();
2. console.info();
3. console.warn();
4. console.error();
5. console.dir();
6. 占位符：%s(只支持字符), &emsp;%d/%i(整数), &emsp;%f(浮点), &emsp;%o(对象)
```
console.log('%d年%d月%d日', 2017, 06, 26);     // '2017年6月26日'

console.log('圆周率 π = ', 3.1415926);         // '圆周率 π =  3.1415926'
```
7. console.dirxml()
```
<div id='app'>hello</div>

var app = document.getElementById('app');

console.dirxml(app);    // <div id='app'>hello</div>
```
8. console.group(); console.groupEnd();
```
console.log(1);             // 1
console.log(2);             // 2
console.group();            // console.grop
console.log(3);             //      3
console.log(4);             //      4
console.groupEnd();
console.log(5);             // 5
```
9. console.dir()
10. console.count() // 执行个数
11. console.time(); console.timeEnd();  // 运行时间
```
console.time('time');
let num = 0;
for(let i = 0; i < 10000000; i++) {
    num++;
};
console.timeEnd('time');

// 'time: 37.84423828125ms'
```
12. console.profile();
13. console.profileEnd();
14. console.assert(boolean, 'contant'); // 断言, 第一个参数为false 时 输出

## 控制台常用快捷键
1. keys, values
```
var obj = {
    name: 'zhangsan',
    age: 18,
    gender: 'male'
};
keys(obj);     // ["name", "age", "gender"]
values(obj);   // ["zhangsan", 18, "male"]
```
2. copy
```
copy(document.body);
```
3. 上下键切换历史命令
4. $_ 最近一次执行命令的结果
5. $0-$5 选中的标签
6. monitor  unmonitor  // 检测入参
7. $ 用法
```
$       // document.querySelector
$$      // document.querySelectorAll
$_      // 上一个表达式的值
$0 - $4 // 最近5个Elements面板选中的DOM元素
```