# Hoisting

> JavaScript **Hoisting** refers to the process whereby the interpreter appears to move the declaration of functions, variables or classes to the top of their scope, prior to execution of the code.

<br />

Thus, variables can appear in code before they are even defined. However, the variable initialization will only happen until that line of code is executed.

```js
    func() // JS

    function func() {
        console.log('JS')
    }
```

> Only the declarations (function and variable) are hoisted

<br />

JS only hoists declarations, **not initializations**. If a variable is used but it is only declared and initialized after, the value when it is used will be the default value on initialization.

<br />

For variables declared with the ```var``` keyword, the default value would be ```undefined```.

```js
    console.log(test) // undefined
    var test; // Declaration
    test = 2022; // Initialization
```
<p align='center'>OR</p>
<br />

```js
    console.log(test) // undefined

    var test = 2022;
```

Logging the ```test``` variable before it is initialized would print ```undefined```. If however, the declaration of the variable is removed, i.e.

```js
    console.log(test) // ReferenceError: test is not defined

    test = 2022; // Initialization
```

a ```ReferenceError``` exception would be thrown because no hoisting happened.


<br />

## **Hoisting functions**

JavaScript functions can be loosely classified as the following:

1. Function declarations
2. Function expressions

We’ll investigate how hoisting is affected by both function types.

<br />

### **Function declarations**


```js
    func() // JS

    function func() {
        console.log('JS')
    }
```

<br />

### **Function expressions**


```js
    console.log(func) // undefined
    func() // Uncaught TypeError: func is not a function

    var func = function() {
        console.log('JS')
    }
```

<p align='center'>OR</p>
<br />

```js
    console.log(func) // undefined
    func() // Uncaught TypeError: func is not a function

    var func = function test() {
        console.log('JS')
    }
```