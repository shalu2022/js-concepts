
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

