### function Statement
```javascript
function sayHi(name){
    return 'Hi' + name;
}
console.log(sayHi('Jasim'));
```
### function Expression 
```javascript
const sayHi = function(name){
    return 'Hi' + name;
}
console.log(sayHI('jasim'));
```
_argument is the default behavior of javascript and all the arguments are like arrray element not exact array._
```javascript
function product(name, price, snipping, availability){
    let info = ' ';
    for(let x of arguments){
        info+= x;
    }
    return info;
}
console.log(product('T-shirt', 20, 0, true))
```
## Rest Operator
```javascript
function RestFunction(name, ...property){
    console.log(`${name} - ${property[0]}`);
}
RestFunction('T-shirt', 30, 0, true);
```
## Default Parameter
// Discount = Discount || 0   
// true -> first one will be executed || otherwise 0
```javascript
function product(name, price, discount = 0.1, shipping, category = 'T-shirt'){
    console.log(name, price, discount, shipping, category);
}
const shirt = product('Printed T-shirt', 30, undefined, true);
console.log(shirt);
```

## Evolution of Function (arrow function)
```javascript
// function add(num1, num2){
//     return num1 + num2;
// }
// const add = function(num1, num2){
//     return num1 + num2;
// }

const add = (num1, num2) => num1 + num2;

```

__Arrow Function and this__
- Arrow function can not bind the value of this.
```javascript
const product = {
    name:'T-shirt',
    price : '$10',
    showInfo:()=>{
        console.log(this);
        return `${this.name} - $${this.price}`; // return undefined
    }

}
```

## Array and Object Destructuring
```javascript
const product = ['T-shirt', 10, 0, true];
//lengthly process
const name = product[0];
const price = product[1];
const snipping = product[2];
const availability = product[3];

// Array Destructuring

const [name, price, snipping, availability] = product;
console.log(name, price, snipping, availability);

// we can use rest operator in destructuring
const [name, price, ...others] = product;
```
```javascript
const product = {
    name: 'T-shirt',
    price: '$10',
    productDesc(){
        return `${this.name} is - $${his.price}`;
    }
}

function productOut({name, price, productDesc}){
    console.log(name, price, productDesc);
}
productOut(product);
```

## First Class Function
```javascript
function greet(){
    console.log('Hi');
}

// we can store a function within a variable like object.
const greet = () => {
    console.log('Hi');
}
// we can return a function inside a function. 
const greet = () => {
    return function(){
        console.log('Hi Jasim');
    }
}
greet()();

// we can pass a function inside a function as a parameter
function greet = (fn) =>{
    console.log(fn());
}
greet(function(){
    return 'Hi';
})
```
 ## Function Statement and Expression
 - In function statement, we can access the function before and after function declaration
 - In function expression, we can access only after the function declaration not before the function declaration.

