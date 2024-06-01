
### Currying is a technique used in functional programming that allows you to transform a function with multiple arguments into a sequence of functions, each taking only one argument at a time. This concept is named after the mathematician Haskell Curry, who introduced it in the 1930s. In JavaScript, currying is a powerful tool that can improve code reusability, composability, and maintainability

### Normal Function
```js
function multiply(a, b, c){
    return a*b*c
}
```
### Curring Function

```js
function multiply(a){
    return function(b){
        return function(c){
            return a*b*c
        }
    }
}
const res = multiply(2)(3)(4)
console.log(res)

```
### Curring Function using arrow function
```js
const add = (a)=> (b)=> a+b

```

### Infinite Curring Function
```js
function add(a){
    return function(b){
        if(b) return add(a+b)
        return a
    }
}
console.log(add(3)(4)(5)(9)())
```
### Infinite Curring Function using arrow 
```js
const add = (a)=>(b)=>b? add(a+b) : a

console.log(add(3)(3)(5)())
```
### Curry Function using Lodash
```js
const {curry} = require('lodash')

function greet(name, wish){
    console.log(`${wish}, ${name}!`)
}

const curriedGreet = curry(greet)

curriedGreet("Adam", "Hello")
curriedGreet("Sara", "Good Evening")
```

#### Currying is a powerful technique that brings several benefits to your JavaScript code. It promotes code reuse, enhances composability, and improves the flexibility of your functions. By transforming functions with multiple arguments into a sequence of functions, currying enables you to create specialized versions and build higher-order functions. Whether you choose to manually curry functions or utilize libraries, currying can be a valuable tool in your functional programming arsenal.
