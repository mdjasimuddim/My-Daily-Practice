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
_Const is same as let_   
__let can not be reassigned and redeclared__

```javascript
if(true){
    const letVariable = 'i am from let';
     letVariable = 'i am from let again';
     console.log(letVariable) //Uncaught TypeError:Assignment to constant variable
}

```






