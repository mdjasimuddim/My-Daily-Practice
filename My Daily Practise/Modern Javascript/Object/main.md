## Object
```Object -> key-value or property-value```
```javascript
const product = {
    name: 'Print T-shirt',
    price: 10,
    'is available': true
}
//Dynamically access properties
const availability = 'is available';
console.log(product.name); //Print T-shirt
console.log(product[name]);
console.log(product['is available']);
console.log(product['availability']);
``` 

### Methods
Method is a javascript function
```javascript
const product = {
    name:'print T-shirt',
    price : 10,
    'is available' : true,
    productDesc : function(){  // methods
        return `${this.name} - $${this.price}`;
    }
}
console.log(product.productDesc())
```

_we can write function in a object without function keyword_
```javascript
const product = {
    name:'print T-shirt',
    price : 10,
    'is available' : true,
    productDesc(){  // methods
        return `${this.name} - $${this.price}`;
    }
}
console.log(product.productDesc())
```

## Factory Function
Create different objects with the same properties and used for:
- to overcome code repetition.
- to overcome multiple object declaration.



```javascript
function product(name, price, availability){
    return {
        name,
        price,
        'is available':availability,
        productDesc(){
            return `${this.name} - $${this.price}`;
        }
    }
}
console.log(product('Print T-shirt', 10, true))
console.log(product('Sneakers', 60, true))
```   

## Constructor Function
Constructor calls once at the time of object creation.
To create different objects with the same properties, we would need to use the keyword "new" and the keyword "this".

```javascript
function Product(name, price){
    this.name = name;
    this.price = price;
    this.productDesc = function(){
        return `${this.name} - $${this.price}`;
    }
}
const product1 = new Product('sneakers', 60);
console.log(product1);
```
```In constructor 'this' means empty object {}, this.name = something means In empty object, we assign name property and something value and back of the scenary, return this and it's default behavior of javascript. ```   
//Camel case firstName  
//Pascel case FirstName   

```Difference - Though, unlike factory functions, constructor functions do not actually return an object. To create different objects with the same properties, we would need to use the keyword "new" and the keyword "this".```


## This keyword 
- this inside method - object
- this in a constructor function - some kind of object
- otherwise - always indicate window

## Call
```first parameter in call function defines the value of this```
```javascript
function sayHi(age, profession){
    console.log(this);
    console.log(`hi ${this}, you are ${age} years old. You are a ${profession}`); // hi jasim, you are 26 years old. You are a Front-end developer
}
sayHi.call('jasim', 26, 'Front-end developer');
```

## Apply
Do same task like call method but rest of the parameter without first paremeter include in an array.

```javascript
function sayHi(age, profession){
    console.log(this);
    console.log(`hi ${this}, you are ${age} years old. You are a ${profession}`); // hi jasim, you are 26 years old. You are a Front-end developer
}
sayHi.apply('jasim', [26, 'Front-end developer']);
```

## Bind
binding the value of this
```javascript
function sayHi(age, professional){
    return `Hi ${this} You are ${age}. You are a ${professional}`
}
const sayHiAfterBinding = sayHi.bind('jasim');
const outputCall = sayHiAfterBinding.call(undefined, 25, 'web developer');
const outputApply = sayHiAfterBinding.apply(undefined, [25, 'web developer']);
console.log(outputCall); //Hi Jasim You are 25. You are a web developer
console.log(outputApply); //Hi Jasim You are 25. You are a web developer
```


_Function expression with bind Method_
```javascript
const sayHi = function(age, professional){
    return `Hi ${this} You are ${age}. You are a ${professional}`;
}.bind('samim');
``` 
## Copy by value / copy by Reference
```javascript
// Copy by value
let a = 10;
const b = a;
console.log(a); //10
console.log(b); //10

a = 20;
console.log(a);  //20
console.log(b);  //10


 // copy be Reference
let obj1 = {value:10};
const obj2 = obj1;
console.log(obj1);  // {value:10}
console.log(obj2);  // {value:10}

obj1.value = 20;

console.log(obj1);  // {value:20}
console.log(obj2);  // {value:20}
```

## Pass by value / Pass by Reference
```javascript
let a = 10;
function passByValue(a){  //pass the copy of value
    a = 20;  
}
passByValue(a);
console.log(a);

let obj = {value : 10};
function passByReferenc(obj){ //pass the copy reference
    obj.value = 20;
}
passByReferenc(obj);
console.log(obj)
```

## Copying Object

```javascript
let product1 = {
    name: 'T-shirt',
    price: 10,
    availability: true
}
let product2 = {};

for(let key in product1){
    product2[key] = product1[key];
}
console.log(product2); // {name:'T-shirt', price : 10, availability:true}


// Another Way
const product3 = Object.assign({}, product1);
console.log(product3); // {name:'T-shirt', price : 10, availability:true}

// Another Way
const product4 = {...product1};
console.log(product4);  // {name:'T-shirt', price : 10, availability:true}
```

## Functions as a object
```javascript
function sayHi(){
    console.log('Hi');
}
sayHi();
sayHi.name = 'jasim'
```
`Behind the seen function works as an object`

