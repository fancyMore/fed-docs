# 词法作用域

## Definition
* JavaScript 的作用域是静态作用域，又叫词法作用域
* 这是因为作用域的嵌套关系可以在语法分析时确定，而不必等到运行时确定。

## Example
```js
var scope = ‘top’; 

var f1 = function() { 
  console.log(scope); 
}; 

f1(); // 输出 top 

var f2 = function() { 
  var scope = ‘f2’; 
  f1(); 
}; 

f2(); // 输出 top 
```

这个例子中，通过 f2 调用的 f1 在查找 scope 定义时，找到的是父作用域中定义的 scope 变量，而不是 f2 中定义的 scope 变量。这说明了作用域的嵌套关系不是在调用 时确定的,而是在定义时确定的。
