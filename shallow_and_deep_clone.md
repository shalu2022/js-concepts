### Shallow copy: means that only the first level of the object is copied. Deeper levels are referenced.
### Deep copy: means that all levels of the object are copied. This is a true copy of the object.

#### Methods used for Shallow copy

1.  object create method

```js 
const obj1 = {
    name: "John",
    age:"36",
    address:{
        city:"LA",
        pin:"123456"
    },
    fun1: function isVerified(){
        return true
    }
}

const obj2 = Object.create(obj1)
obj2.address.city = "austin"

console.log("obj1", obj1) //city:"austin"
console.log("obj2", obj2) //city:"austin"
```
2. object assign method
```js
const obj1 = {
    name: "John",
    age:"36",
    address:{
        city:"LA",
        pin:"123456"
    },
    fun1: function isVerified(){
        return true
    }
}

const obj2 = Object.assign({}, obj1)
obj2.address.city = "austin"

console.log("obj1", obj1) //city:"austin"
console.log("obj2", obj2) //city:"austin"
```
3. spread operator
```js
const obj1 = {
    name: "John",
    age:"36",
    address:{
        city:"LA",
        pin:"123456"
    },
    fun1: function isVerified(){
        return true
    }
} 

const obj2 = {...obj1}
obj2.address.city = "austin"

console.log("obj1", obj1) //city:"austin"
console.log("obj2", obj2) //city:"austin"
```

#### Methods used for Deep copy

1. JSON.parse(JSON.stringify(object))

```js
const obj1 = {
    name: "John",
    age:"36",
    address:{
        city:"LA",
        pin:"123456"
    },
    fun1: function isVerified(){
        return true
    }
} 

const obj2 = JSON.parse(JSON.stringify(obj1))
obj2.address.city = "austin"

console.log("obj1", obj1) //city:"LA"
console.log("obj2", obj2) //city:"austin"
```
2. Structure Clone
```js
const obj1 = {
    name: "John",
    age:"36",
    address:{
        city:"LA",
        pin:"123456"
    },
    //do not include funtion as it will throw error
    // fun1: function isVerified(){
    //     return true
    // }
} 

const obj2 = structuredClone(obj1)
obj2.address.city = "austin"

console.log("obj1", obj1) //city:"LA"
console.log("obj2", obj2) //city:"austin"

```
3. lodash clonedeep
```
const _ = require('lodash');
let deepCopy = _.cloneDeep(obj);