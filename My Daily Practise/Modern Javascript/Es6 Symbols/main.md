## Symbols in Javascript

#### How to declare symbol ?
```javascript
var symbol1 = Symbol();
console.log(symbol1);

var symbol2 = Symbol();

console.log(symbol1 === symbol2); //symbols are unique


var symbol3 = Symbol("I am symbol with description"); // Symbol Description
```

_We can not create symbol like this new keyword_:
```javascript
let str = "Jasim";
let str2 = new String("Jasim");
```
__Symbol will be equal using for__
```javascript
var name1 = Symbol.for("name1");
var name2 = Symbol.for("name1");
console.log(name1 == name2);
```

__We can use Symbol as an Object key/property__

```javascript
var cricket = Symbol.for("This is cricket Symbol");
var object = {
    name: "Sakib",
    [cricket]: 3
}
```

### Why do you need symbols ?
to avoid or hidden the property of object in iterate or as usual, we can use symbols
```javascript
let object = {};
object.name = "Javascript"
object.std = "1995";

object[Symbol("founder")] = "Brenden Eich";
console.log(Object.keys(object));  // name, std

//  for in loop
for (let x in object){
    console.log(object[x]);  // Javascript, 1995
}
```

### Symbol in Array
```javascript
var includes = Symbol("my own array includes method");
Array.prototype[includes] = () => {
    console.log("This is my array includes function");
}
var myArray = [1, 2, 3];
console.log(myArray.includes(2));
console.log(myArray.["includes"](2));
myArray[includes](2)
 ```
 `In the back-end, Javascript use huge symbol.Using Symbol we can create includes, charAt, charCodeAt etc.`


 ```javascript
class Product{
    constructor(title){
        this.title = title;
    }
    [Symbol.search](string){
        return string.indexOf(this.title) >= 0 ? "Found" : "Not found";
    }
}

var laptop = new Product("laptop");

 ```
