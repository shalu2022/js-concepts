
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
