## Scope
<p>Child can access all the parent elements but parent can not access the child elements.</p>   
<br/>

```javascript
var x = 12;
//parent
function myFunc(){
    var y = 10;
    //child
    console.log(`${x} from myFunc()`);   //12
}
myFunc()
console.log(x)  //12
```

```javascript
//parent
function myFunc(){
    var x = 10;
    //child
    console.log(`${x} from myFunc()`);   //10
}
myFunc()
console.log(x)  //x is not defined
```

__Javascript Variable Var can override the value of parent element and give the access to child__   
Example:
```javascript
var x = 12;
//parent
function myFunc(){
     x = 10;
    //child
    console.log(`${x} from myFunc()`);   //10
}
myFunc()
console.log(x)  //10
```


### More Weird thing in Javascript scoping 
```javascript
//parent
function myFunc(){
     x = 10;
    //child
    console.log(`${x} from myFunc()`);   //10
}
myFunc()
console.log(x)  //10
```
__But we can solve this above issue using "use strict" Mode__
```javascript
'use strict'
//parent
function myFunc(){
     x = 10;
    //child
    console.log(`${x} from myFunc()`);   // x is not definded
}
myFunc()
console.log(x)  // x is not defined
```
## var variable
__Using Var__   
var is function scope and we can access it outside of block 
```javascript
if(true){
    var varVariable = 'i am from var';
}
console.log(varVariable) // i am from var
```
__Using Let__   
let is block scope and we can not access it outside of block
```javascript
if(true){
    let letVariable = 'i am from var';
}
console.log(varVariable) // ReferenceError: x is not definded
```

__var can be redeclared__
```javascript
var varVariable = 'i am from var';
console.log(varVariable) // i am from var
if(true){
    var varVariable = 'i am from var again';
}
console.log(varVariable) // i am from var again
```
## let variable
__let can not be redeclared__
```javascript
if(true){
    let letVariable = 'i am from let';
    let letVariable = 'i am from let again';
}
console.log(letVariable) // Uncaught SyntaxError: Identifier 'letVariable' has already been declared
```

__But let can  be reassigned__
```javascript
if(true){
    let letVariable = 'i am from let';
     letVariable = 'i am from let again';
     console.log(letVariable) //i am from let again
}

```
## const variable
_Const is same as let_   
__const can not be reassigned and redeclared__

```javascript
if(true){
    const letVariable = 'i am from let';
     letVariable = 'i am from let again';
     console.log(letVariable) //Uncaught TypeError:Assignment to constant variable
}

```


## Dynamic Typing
passing data type with the value.
```javascript
let productName = "Mango"
typeof productName  //String
productName = true
typeof productName  //Boolean
```

### Infinite loop
```javascript
const text = ` i don't repeat my code `;
let number =  1;
while(number<6){
    console.log(`${text} is repeated infinite times until the browser crashes. `);
}
```
_Due to the condition is always true._   

### Dynamically access properties
```javascript
const profile = {
    firstName:'jasim',
    lastName:'uddim',
    age:26,
    profession:'web developer'
}
const surName = 'firstName'
console.log(profile[surName]) // dynamically access value 

for(let x in profile){
    console.log(profile[x])  // dynamically access value
}
```
## Execution context of Javascript
1. Interpreter
    - Slow Process
    - Easy to Debug
2. Compiler
    - Faster Process
    - System Crash & Hard to debug

__Mainly, Javascript work on Just-in-time (JIT) Compiler__

_Execution Context - do small pieces of code._
