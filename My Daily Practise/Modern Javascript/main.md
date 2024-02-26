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
console.log(x)  //undefined
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

