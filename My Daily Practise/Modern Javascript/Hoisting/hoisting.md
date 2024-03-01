__Hoisting is the Javascript's default behavior of moving declarations to the top.__
```let and const are hoisted to top but not initialized```

### Example of Hoisting
```javascript
a = 10;
console.log(a);
var a;
```

_But let and const_:   
```javascript
//let a  ##Befind the seen, let will be stay in temporal dead zone
a = 10;
console.log(a);
let a;
```
In Function, do the same thing
```javascript
function A(){
    x = 5;   
    console.log(x); // show Reference error 
    let x;
}
A();
```

_For using const, code will be show syntactically error_
```javascript
// it's not possible to assign the value without declaration in Const
x = 5;
const x;
```

```javascript
//Behind the seen, var will work like below.
var x = 10;
var y = 20;
var x;
x = 10;
var y; 
y = 20;
```
