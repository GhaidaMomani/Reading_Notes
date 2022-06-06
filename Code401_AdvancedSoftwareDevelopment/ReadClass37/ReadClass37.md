# Reading_Notes
## Code 401 - Advanced Software Development





By [Ghaida Al Momani] (https://github.com/GhaidaMomani).


<br/>
<hr/>
<br/>


# ES6 Syntax and Feature Overview

[Link to the article](https://www.taniarascia.com/es6-syntax-and-feature-overview/)

ECMAScript 2015, also known as ES6, introduced many changes to JavaScript. Here is an overview of some of the most common features and syntactical differences, with comparisons to ES5 where applicable.


The sixth edition of ECMAScript – the scripting language specification by which JavaScript is standardized – introduced many new features, upgrades, and shortcuts to the JavaScript programming language. This version is commonly known as ECMAScript2015 or ES6.


**What is ES6?**
ES6 stands for ECMAScript 6.

ECMAScript was created to standardize JavaScript, and ES6 is the 6th version of ECMAScript, it was published in 2015, and is also known as ECMAScript 2015.

**Why Should I Learn ES6?**
React uses ES6, and you should be familiar with some of the new features like:

Classes
Arrow Functions
Variables (let, const, var)
Array Methods like .map()
Destructuring
Modules
Ternary Operator
Spread Operator




**Classes**
ES6 introduced classes.

A class is a type of function, but instead of using the keyword function to initiate it, we use the keyword class, and the properties are assigned inside a constructor() method.

Example
A simple class constructor:
```js
    class Car {
    constructor(name) {
        this.brand = name;
    }
    }
```


**Arrow Functions**
Example
```js
    hello = () => {
    return "Hello World!";
    }

```

**Variables**

Before ES6 there was only one way of defining your variables: with the var keyword. If you did not define them, they would be assigned to the global object. Unless you were in strict mode, then you would get an error if your variables were undefined.

Now, with ES6, there are three ways of defining your variables: var, let, and const.
```js   
    var
    var x = 5.6;
```
If you use var outside of a function, it belongs to the global scope.

If you use var inside of a function, it belongs to that function.

If you use var inside of a block, i.e. a for loop, the variable is still available outside of that block.

var has a function scope, not a block scope.
```js
    let
    let x = 5.6;
```
let is the block scoped version of var, and is limited to the block (or expression) where it is defined.

If you use let inside of a block, i.e. a for loop, the variable is only available inside of that loop.

let has a block scope.


**Array Methods**
There are many JavaScript array methods.

One of the most useful in React is the .map() array method.

The .map() method allows you to run a function on each item in the array, returning a new array as the result.

In React, map() can be used to generate lists.

Example
```js
Generate a list of items from an array:

const myArray = ['apple', 'banana', 'orange'];

const myList = myArray.map((item) => <p>{item}</p>)
```


**Destructuring**
To illustrate destructuring, we'll make a sandwich. Do you take everything out of the refrigerator to make your sandwich? No, you only take out the items you would like to use on your sandwich.

Destructuring is exactly the same. We may have an array or object that we are working with, but we only need some of the items contained in these.

Destructuring makes it easy to extract only what is needed.

Destructing Arrays
Here is the old way of assigning array items to a variable:

Before:
```js
    const vehicles = ['mustang', 'f-150', 'expedition'];

    // old way
    const car = vehicles[0];
    const truck = vehicles[1];
    const suv = vehicles[2];
    Here is the new way of assigning array items to a variable:
```            
With destructuring:
```js
    const vehicles = ['mustang', 'f-150', 'expedition'];

    const [car, truck, suv] = vehicles;
    When destructuring arrays, the order that variables are declared is important.
 ```

**Spread Operator**
The JavaScript spread operator (...) allows us to quickly copy all or part of an existing array or object into another array or object.

Example
```js
    const numbersOne = [1, 2, 3];
    const numbersTwo = [4, 5, 6];
    const numbersCombined = [...numbersOne, ...numbersTwo];  
``` 


**Modules**
JavaScript modules allow you to break up your code into separate files.

This makes it easier to maintain the code-base.

ES Modules rely on the import and export statements.

Export
You can export a function or variable from any file.

Let us create a file named person.js, and fill it with the things we want to export.

There are two types of exports: Named and Default.

Named Exports
You can create named exports two ways. In-line individually, or all at once at the bottom.

In-line individually:
person.js
```js
    export const name = "Jesse"
    export const age = 40
```
    All at once at the bottom:
    person.js
```js
    const name = "Jesse"
    const age = 40
    export { name, age }
```


**Ternary Operator**
The ternary operator is a simplified conditional operator like if / else.

Syntax: condition ? <expression if true> : <expression if false>

Here is an example using if / else:

Before:
```js
    if (authenticated) {
    renderApp();
    } else {
    renderLogin();
    }
```
Here is the same example using a ternary operator:

With Ternary
```js
    authenticated ? renderApp() : renderLogin();
```

<hr/>
<p align="right">(<a href="#top">back to top</a>)</p>
<br/><br/>
<p align="right">Ghaida Al Momani, Software Engineer</p>
<p align="right">Jordan, Amman</p>
<p align="right">22, 6 June </p>