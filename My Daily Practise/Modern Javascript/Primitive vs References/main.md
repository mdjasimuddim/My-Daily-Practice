## Primitive Data Type
- Number
- String
- Boolean
- Null
- Undefined
- Symbol (Es6)

```javascript
var a = 5;
var b = a;

b = 6;
// Expected behavior
console.log(a);
console.log(b);
```

## Reference Data Type
Some how they are the instance of Object(Master Object)
- Object
- Array
- Function
- Date 
```javascript
var a = {
    person:"Tamim"
};
var b = a;

b.person = "Sakib";  //mutation
// Unexpected behavior
console.log(a);
console.log(b);
```

```javascript
var a = ['Tamim', 'Sakib'];
var b = a;

b.push('Karim');
// Unexpected behavior
console.log(a);
console.log(b);
```
In Javascript, mutation and assignment both are not same.
```javascript
var a = {
    person:"Tamim"
};
var b = a;

// b.person = "Sakib";
a =[];  //assignment
// Unexpected behavior
console.log(a);
console.log(b);
```

### Immutably (without change)
```javascript
var language = {
    name: "Javascript",
    estd: "1995"
}
var language2 = {...language};  // we can it do using lodash _.clone() more accurately. 
language.founder = "Brendan Eich";

console.log(language2);
console.log(language);
```


### Pass by Reference/value

```javascript
let a = 1;
let change = (val) => {
    val = 2;
}
change(a);   // looks like passed by value but Reference type
console.log(a);  //1
```

__In Javascript function, passing parameter in a function from outside is always passed by Reference.__
