# JS

1. 介绍JavaScript的基本数据类型

   String、Number、Object、Undefined、Null、Boolead是六大基本数据类型

   ES6新增一种数据类型：Symbol。表示独一无二的值

2. 什么是空对象？怎么判断是不是空对象？

   i：当一个对象的引用是null时，该对象就是空对象；

   a：当对象的所有属性的[[Enumerable]]特性值为false（即该对象所有属性都不可枚举），那么这个对象就是空对象

   - 判断是否为空对象？

     1. `for...in`遍历属性，为真则为非空对象，否则为空对象

        ```js
        for (var i in obj) { // 如果不为空，则会执行到这一步，返回true
            return true
        }
        return false // 如果为空,返回false
        ```

     2. 通过JSON自带的方法`stringfy()`进行判断

        ```js
        if (JSON.stringify(data) === '{}') {
            return false // 如果为空,返回false
        }
        return true // 如果不为空，则会执行到这一步，返回true
        ```

     3. `Object.keys()`

        `Object.keys()`方法会返回一个由一个给定对象的自身可枚举属性组成的数组

        如果对象为空，它会返回一个空数组，如下：

        ```js
        var a = {}
        Object.keys(a) // []
        ```

        我们可以依靠Object.keys()这个方法通过判断它的长度来知道它是否为空

        ```js
        if (Object.keys(object).length === 0) {
            return false // 如果为空,返回false
        }
        return true // 如果不为空，则会执行到这一步，返回true
        ```

3. let和const的区别以及他们产生的原因？

   me：let 定义的是变量，const定义的是常量；因为js中是没有块作用域的，在循环中使用var定义的变量，在循环结束之后往往不会消失，使用let定义，可以形成块作用域，只会作用于当前作用域；let新增了js的块级作用域

4. 改变this的方法有哪些？

   me：call、apply、bind

5. call、apply、bind方法是在原函数上定义的吗？

   call、apply与bind是在Funtion的原型上定义的方法；

6. 介绍一下js有哪些作用域？

   me：全局作用域与局部作用域

   ans：词法作用域与函数作用域

   发散一波：什么是作用域？什么是词法作用域？什么是函数作用域？

   - 作用域：它是一套规则，用于确定在何处以及如何查找变量
   - 词法作用域：意味着作用域是由书写代码时函数声明的位置来决定的  //不太明白
   - 函数作用域：每个函数都会创建一个自身的函数作用域，在该函数之外无法访问函数内部创建的变量，声明一个函数内部的变量或函数会在所处的作用域中隐藏起来

7. 怎样生成块级作用域？

   me：使用let方法

   ans：1.es6let方法；2.闭包(也是匿名函数) ;3.匿名函数

   ```js
   //无作用域模板
   for(var i=0;i<5;i++){
   }
   alert(i) // 5
   //方法1：let
   for(let i=0;i<5;i++){
   }
   alert(i); //ReferenceError: j is not defined
   //方法2：匿名函数
   (function(){
       for(var j=0;j<5;j++){
           
       }
   })();
   alert(j);//报错：ReferenceError: j is not defined
   ```

   注意：function(){}();会报错，因为function(){}会被认为是函数声明，而不是函数表达式；而函数声明后不能跟圆括号

8. ES6 class是怎么实现的？与ES5 function的区别





