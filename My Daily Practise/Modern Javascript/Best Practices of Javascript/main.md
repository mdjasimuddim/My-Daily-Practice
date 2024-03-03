### Best Practices No. 01

## Variable Naming 1
Give the meaningful name of variable.

```javascript
// Bad Practice
let day11 = 10;
let ok;
if(day11 < 30){
    ok = true;
}
// Good Practice
const MAX_ALLOWED_LOGIN_EXPIRATION_DAYS = 30;
let daysSinceLastLogin = 10;

const isUserLoggedIn = daysSinceLastLogin < MAX_ALLOWED_LOGIN_EXPIRATION_DAYS;

```
### Best Practices No. 02
## Variable Naming 2
avoid the extra word of variable name.
```javascript
// Bad Practice
let nameValue;
let theProduct;
// Good Practice
let name;
let product;

```
### Best Practices No. 03
## Variable Naming 3
Give the variable name like that do not remain the purpose of Variable name.
```javascript
// Bad Practice
const products = ["T-shirt", "Shoes", "Watches", "Bags"];
products.forEach((p)=>{
    doSomething();
    // what does `p` stands for
    doSomethingElse(p);
})
// Good Practice

const products = ["T-shirt", "Shoes", "Watches", "Bags"];
products.forEach((product)=>{
    doSomething();
    doSomethingElse(product);
})
```

### Best Practices No. 04
## Variable Naming 4
no need to add the unnecessary context.
```javascript
// Bad Practice
const product = {
    productId: 1,
    productName: "T-shirt",
    productPrice: 8.99,
    productUnits: 2
}
// Good Practice
const product = {
    id: 1,
    name: "T-shirt",
    price: 8.99,
    units: 2
}
```

### Best Practices No. 05
## Function Naming
try to give the function name as long and descriptive
```javascript
// Bad Practice
function email(user){
    // implementation
}
// Good Practice
function sendEmailToUser(email){
    // implementation
}
```

### Best Practices No. 06
## Function Arguments 01
avoid too much arguments
```javascript
// Bad Practice
function getProducts(fields, formDate, toDate){
    // implementation
}
// Good Practice
function getProducts({fields, formDate, toDate}){
    // implementation
}
```
### Best Practices No. 07
## Function Arguments 02
use default arguments, not conditionals
```javascript
// Bad Practice
function createShape(type){
    const shapeType = type || "circle";
}
// Good Practice
function createShape(type = "circle"){
    // .....
}
```

### Best Practices No. 08
## Function Arguments 03
no need to send flag variable as a parameter
```javascript
// Bad Practice
function createFile(name, isPublic){
    if(isPublic){
        fs.create(`./public/${name}`)
    }else{
        fs.create(name);
    }
}
// Good Practice
function createFile(name){
    fs.create(name);
}
function createPublicFile(name){
    createFile(`./public/${name}`);
}
```
### Best Practices No. 09
## Single task for function
it's not good to do multiple work inside a function
```javascript
// Bad Practice
function notifyUsers(users){
    users.forEach((user)=> {
        const userRecord = database.lookup(user);
        if(userRecord.isVerified()){
            notify(user);
        }
    })
}
// Good Practice
function notifyVerifiedUsers(users){
    users.filter(isUserVerified).forEach(notify);
}
function isUserVerified(user){
    const userRecord = database.lookup(user);
    return userRecord.isVerified();
}
```

### Best Practices No. 10
## Type Checking
always check strong Type
```javascript
1 == "1"  //true
1 === "1"  //false

0 == false // true
0 === false // false

// full example
const val = "123";
if(val == "123"){
    //reachable
    console.log(`1. ${val}`);
}
if(val == 123){
    //reachable
    console.log(`2. ${val}`);
}

if(val === 123){
    //unreachable
    console.log(`2. ${val}`);
}
if(val === "123"){
    //reachable
    console.log(`2. ${val}`);
}
```

### Best Practices No. 11
## Default Object value
use `Object.assign` to set default object value
```javascript
// Bad Practice
const shapeConfig = {
    type: "circle",
    width: 150,
    height: null
}
function createShape(config){
    config.type = config.type || "circle";
    config.width = config.width || 300;
    config.height = config.height || 300;
}
createShape(shapeconfig)
// Good Practice
const shapeConfig = {
    type: "circle",
    width: 150,
    // Exclude the height key
}
function createShape(config){
    config = Object.assign({
        type:"circle",
        width:300,
        height:300
    }, config)
}
createShape(shapeconfig)
```

### Best Practices No. 12
## Prototype Pollution
it's not good to pollute global prototypes.
```javascript
// Bad Practice
Array.prototype.myFunction = function myFunction(){
    // implementation
}
// Good Practice
class MyArray extends Array{
    myFunc(){
        // implementation
    }
}
```
### Best Practices No. 13
## Conditional Shorthand
use conditional shorthand
```javascript
// Bad Practice
if(isValid === true){
    // do something
}
if(isValid === false){
    // do something
}
// Good Practice
if(isValid){
    // do something
}
if(!isValid){
    // do something
}
```

### Best Practices No. 14
## Method Chaining
use method chaining
```javascript
// Bad Practice
class Product{
    constructor(name){
        this.name = name;
    }
    setUnits(units){
        this.units = units;
    }
    setPrice(price){
       this.price = price; 
    }
    save(){
        console.log(this.name, this.units, this.price);
    }
}
const product = new Product("Bag");
product.setPrice(23.99);
product.setUnits(13);
product.save();

// Good Practice
class Product{
    constructor(name){
        this.name = name;
    }
    setUnits(units){
        this.units = units;
        return this;
    }
    setPrice(price){
       this.price = price;
       return this; 
    }

    save(){
        console.log(this.name, this.units, this.price);
    }
}
const product = new Product("Bag").setPrice(600).setUnits(2).save();
```

### Best Practices No. 15
## Avoid evail()
avoid using eval
```javascript
eval("alert('alert');");
```
### Best Practices No. 16
## Curly Braces
don't try omit curly braces and use shorthand
```javascript
// Bad Request
if(someVariableExists)
    x = false;

if(someVariableExists)
    x = false;
    anotherFunctionCall();

// one might think that the code above would be equivalent to:
if(someVariableExists){
    x = false;
    anotherFunctionCall();
}
```

### Best Practices No. 17
## Prototype Methods
Add methods on the .prototype when writing constructors
```javascript
// Bad Practice
function Player(name, age){
    this.name = name;
    this.age = age;

    this.play = function(){
        console.log(`${this.name} is playing`);
    }
}

// Good Practice
function Player(name, age){
    this.name = name;
    this.age = age;
}
Player.prototype.play = function(){
        console.log(`${this.name} is playing`);
}
let sakib = new Player("Sakib", 37);
let tamim = new Player("Tamim", 36);
sakib.play();
```

### Best Practices No. 18
## for loop
Declare variables outside of the for statement
```javascript
// Bad Practice
for(var i = 0; i < someArray.length; i++){
    var container = document.getElementById('container');
    container.innerHTML += "my number :"+i;
    console.log(i);
}

// Good Practice
var container = document.getElementById('container');
let len = someArray.length;
for(var i = 0; i < len; i++){
    container.innerHTML += "my number :"+i;
    console.log(i);
}
```
### Best Practices No. 19
## let const 
use let const as much as possible instead of var.

### Best Practices No. 20
## Usage of var
omit the "var" keyword and use commas instead

```javascript
// bad
var someItem = "some string";
var anotherItem = "another string";
var onMoreItem = "one more String";

// better
var someItem = "some string",
anotherItem = "another string",
onMoreItem = "one more String"
```

### Best Practices No. 21
## Use semicolon
always use semicolon

```javascript
// bad
var someItem = 'some string'
function doSomething(){
    return 'something'
}
// good
var someItem = 'some string';
function doSomething(){
    return 'something';
}
```
### Best Practices No. 22
## Use IIFE
use IIFE as much as possible

```javascript
(function doSomething(){
    return{
        name:'sakib',
        lastName:'hasan'
    }
})()
```

### Best Practices No. 23
## module Pattern
avoid using global

```javascript
// bad
var current = null;
function init(){
    // do something
}
function change(){
    // do something
}
function verify(){
    // do something
}
// good
const myModule = (function(){
    var current = null;
    function init(){
        // do something
        console.log("init");
    }
    function change(){
    // do something
    }
    function verify(){
        // do something
    }
    return {
        init, 
        change,
        present: current
    }
})()
myModule.init();
```