# Closure

A closure is the combination of a function and the lexical environment within which that function was declared.

## Functions are assigned by value reference

```js
function sayHello() {
  console.log("hello");
};
var func = sayHello;
```
Result:
```js
func.answer = 42;
console.log(sayHello.answer); // prints 42
```

Now let’s see an example of closure within a loop.
```js

// Outer function 
function outer()  
{ 
    var arr = []; 
    var i; 
    for (i = 0; i < 4; i++)  
    { 
        // storing anonymus function 
        arr[i] = function () { return i; } 
    } 
  
    // returning the array. 
    return arr; 
} 
  
var get_arr = outer(); 
  
console.log(get_arr[0]()); //4
console.log(get_arr[1]()); //4
console.log(get_arr[2]()); //4
console.log(get_arr[3]()); //4
```

 Four closures have been created by the loop, but each one shares the same single lexical environment, which has a variable with changing values

Lets see an correct way to write the above code so as to get different values of i at different index.

// Outer function 
```js
function outer()  
{ 
    function create_Closure(val)  
    { 
        return function()  
        { 
            return val; 
        } 
    } 
    var arr = []; 
    var i; 
    for (i = 0; i < 4; i++)  
    { 
        arr[i] = create_Closure(i); 
    } 
    return arr; 
} 
var get_arr = outer(); 
console.log(get_arr[0]()); 
console.log(get_arr[1]()); 
console.log(get_arr[2]()); 
console.log(get_arr[3]()); 
```