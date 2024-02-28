## Closures
When we return function in a parent function, then child function can access all the variable, function or object from a parent function that is called Closures.

```javascript
var sum = function(num1, num2){
    return num1 + num2;
}
console.log(sum(2,3))
```

```javascript
var num1 = 10;
var num2 = 20;
var sum = function(){
    return num1 + num2;
}
console.log(sum())
```

```javascript
var num1 = 10; //scope
var sum = function(){
    var num2 = 20; //closure
    return function(){
        return num1 + num2;
    } 
}
console.log(sum())
```
```javascript
    function bankAccount(initialBalance){
        var balance = initialBalance;
        return function(){
            return balance;
        }
    }
    const account = bankAccount(10000);
    console.log(account());
```

_closures can secure private property and variables that are used locally, but defined in an enclosing scope._ 

```javascript
(function(){
    var num1 = 2;
    var num2 = 3;

    var sum = function(){
        return num1 + num2;
    }
    console.log(sum());
    console.log(sum);

    num1 = 6;
    num2 = 7;
    
    console.log(sum());
    console.log(dir);
})()
```

### Closure Using let
```javascript
(function(){
    let num1 = 2;
    let num2 = 3;

    var sum = function(){
        return num1 + num2;
    }
    console.log(sum());
    console.dir(sum);
})()
```

### Asynchronous Javascript with closure
```javascript
(function(){
    var a = 20;

    var myFunc = () =>{
        console.log(a);
    }
    setTimeout(myFunc, 3000);
    console.dir(myFunc);
})()
``` 