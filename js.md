### 001.Promise原理？

[异步解决方案](https://juejin.im/post/6844903896486264845)

### 002.then可以链式调用，多个then时，如何走到下一个then的失败回调？

答:
 1.返回一个失败的promise。
 2.抛出一个错误(throw new Error())

### 003.then可以链式调用，多个then时，如何终止下一个then的调用？

答：返回一个处于pending(等待态)状态的promise

### 004.js的异步解决方案有哪些？

答：

- 回调函数（嵌套，回调地狱，不优雅）
- Promise
- Generator+co （co可以解决promise嵌套问题，generator+promise(promise嵌套问题)）
- async+await：是Generator的语法糖

### 005.把一个伪数组变成真实的数组？

答：

- [...obj]，需要保证obj是可迭代的
- Array.from不需要保证obj是否迭代，内部会使它可迭代

### 006.使用过ES6中哪些新语法(重点 * 熟练使用ES6语法)？

答：

- 结构赋值 [] {}
- 展开运算符（...args）(考察深拷贝，浅拷贝)
- Set：常用于数组去重
- Map：里面存储唯一的值

> 深拷贝实现的一种方式：JSON.parse(JSON.strinfy(obj));

[ES6 新增内容总结](https://juejin.im/post/6844903902031118344)

### 007.实现深拷贝（重点）浅拷贝？

[理解JS中的浅拷贝与深拷贝](https://juejin.im/post/6844903962424934407#heading-8)

```javascript
function deepClone(source) {
    const targetObj = source.constructor === Array ? [] : {}; // 判断复制的目标是数组还是对象
    for (let keys in source) { // 遍历目标
        if (source.hasOwnProperty(keys)) {
            if (source[keys] && typeof source[keys] === 'object') { // 如果值是对象，就递归一下
                targetObj[keys] = source[keys].constructor === Array ? [] : {};
                targetObj[keys] = deepClone(source[keys]);
            } else { // 如果不是，就直接赋值
                targetObj[keys] = source[keys];
            }
        }
    }
    return targetObj;
}

var str1 = {
    arr: [1, 2, 3],
    obj: {
        key: 'value'
    },
    fn: function () {
        return 1;
    }
};
var str3 = deepClone(str1);

console.log(str3 === str1); // false
console.log(str3.obj === str1.obj); // false
console.log(str3.fn === str1.fn); // true
复制代码
```

### 008.求数组的交集、并集、差集？

答：

```javascript
//-----------------------------------------并集
// let arr1 = [1, 2, 3, 4]
// let arr2 = [3, 4, 5, 6]

//并集
// function union(arr1, arr2) {
//     // let s1 = new Set(arr1)
//     // let s2 = new Set(arr2)
//     // let s = new Set([...s1,...s2])
//     // return [...s]

//     let s = new Set([...arr1,...arr2])
//     return [...s]
// }

// console.log(union(arr1,arr2));  //[ 1, 2, 3, 4, 5, 6 ]

//-----------------------------------------交集
// let arr1 = [1, 2, 3, 4]
// let arr2 = [3, 4, 5, 6]

// //交集
// function intersection(arr1,arr2){
//     let s1 = new Set(arr1)
//     let s2 = new Set(arr2)
//     return [...s1].filter(item=>{
//         return s2.has(item)
//     })
// }

// console.log(intersection(arr1,arr2))    //[ 3, 4 ]

//-----------------------------------------差集
// let arr1 = [1, 2, 3, 4]
// let arr2 = [3, 4, 5, 6]

// function difference(arr1,arr2){
//     let s1 = new Set(arr1)
//     let s2 = new Set(arr2)
//     return [...s1].filter(item=>{
//         return !s2.has(item)
//     })
// }

// console.log(difference(arr1,arr2))      //[ 1, 2 ]
复制代码
```

### 009.ES6中的模块化？

答：[ES6模块化](https://juejin.im/post/6844903959904288782)

ES6 的模块化分为导出（export） @与导入（import）两个模块。

as 的用法

### 010.模块化的发展流程？

不做深入理解

### 011.JS中的闭包(重点)

[JS中的 闭包(Closure)](https://juejin.im/post/6844903930082623496)

### 012.浏览器事件环 (重点 * 宏、微任务)

[JS(浏览器)事件环 (宏、微任务)](https://juejin.im/post/6844903914085564423)

### 013.ES6新增了哪些内容，简单说一下

[ES6 新增内容总结](https://juejin.im/post/6844903902031118344)

### 014.对JS原型和原型链的理解？

[JavaScript 原型 与 原型链](https://juejin.im/post/6844903901091594253)

### 015.对JS作用域和作用域链的理解？

[JavaScript 作用域 与 作用域链](https://juejin.im/post/6844903901074980871)

### 016.JS中new究竟做了什么？

1.创建对象
 2.绑定this
 3.链接到原型
 4.返回对象
 [JS中 new究竟做了什么？](https://juejin.im/post/6844903896326864910)

### 017.JS中this到底指向谁？怎么改变this指向？

**谁调用了包含this的方法，那么this就指向谁**
 [JS中的 this 到底指向谁？](https://juejin.im/post/6844903896188452878)

改变this，可以用call、apply、bind，他们之间的区别？
 [JS中改变this的指向 call、apply 和 bind 的区别](https://juejin.im/post/6844903895743856654)

### 018.TS主要是干什么的？

简单地说，TS就是增加了重要的类型检测机制，添加了很多类型，可以用来写大型项目。
 布尔值、数字、字符串、数组、元组、枚举、any、void、null、undefined、never、object、类型断言

### 019.JS中的方法（重中之重）

[JS常用方法总结](https://juejin.im/post/6844903898189152263)

### 020.JS中的数据类型?

JavaScript中有6种数据类型：数字（number）、字符串（string）、布尔值（boolean）、undefined、null、对象（Object）。

其中对象类型包括：数组（Array）、函数（Function）、还有两个特殊的对象：正则（RegExp）和日期（Date）。