
### call
The call method invokes a function with a specified "this" value and arguments provided individually.
```js
function greet(greet1, greet2) {
    console.log( `${greet1} ${this.firstName} ${this.lastName}, ${greet2}`)
}
const person = {
    firstName: 'Shalu',
    lastName: 'Chaddha'
};

greet.call(person, "Hello", "How are you?");

// Output: Hello Shalu Chaddha, How are you?

```
### apply
 The apply method is similar to call, but it accepts arguments as an array or an array-like object.
```js
greet.apply(person, ["Hello", "How are you?"]);
// Output: Hello Shalu Chaddha, How are you?

```

### bind
The bind method creates a new function that, when called, has its this keyword set to a specified value, with a given sequence of arguments preceding any provided when the new function is called.

#### syntax
```js
function.bind(thisArg, arg1, arg2, ...)
```
```js
const greetingUser = greet.bind(person);

console.log(greetingUser("Hello", "How are you?"))
// Output: Hello Shalu Chaddha, How are you?

```
### Example of using Call, Bind and Apply

```js
const Calculator = {
    value: 0,
    add: function(num1, num2){
         return this.value+=(num1+num2)
    },
    subtract: function(num){
        return this.value -= num
    }
}

const userValue = {
    value: 8
}

// Using call to invoke subtract with 'this' set to userValue.It is invoked immediately and take arguments individually 
console.log(Calculator.subtract.call(userValue, 5))
// Using apply to invoke add with 'this' set to userValue. It is invoked immediately and take arguments in array
console.log(Calculator.add.apply(userValue, [5, 3]))
// Using bind to create a new function with 'this' bound to userValue and take arguments individually.
console.log(Calculator.add.bind(userValue, 5, 3)())

```

