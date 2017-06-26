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
