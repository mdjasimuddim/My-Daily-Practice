## Currying
Currying is a functional programming pattern.

```javascript
function multiply(a, b, c){
    return a * b * c;
}

console.log(multiply(5, 6, 7));


// Currying Function converts multiple parameter to single parameter

function multipleCurrying(a){
    return function(b){
        return function(c){
            return a * b * c;
        }
    }
}

let step1 = multipleCurrying(5);
let step2 = step1(6);
let step3 = step2(7);
console.log(step3);
```


```javascript
function discount(price, discount){
    return price - price * discount;
}
console.log(discount(700, 0.1));

// Equivalent Currying function 
function discount (disc){
    return function(price){
        return price - price * disc;
    }
}
// currying is a combination of multiple partial function.
let discountFunc = discount(0.1);  //partial function
let customer1 = discountFunc(700);
let customer2 = discountFunc(800);
let customer3 = discountFunc(900);
console.log(customer1, customer2, customer3);
```


```javascript
// curry converter
function curry(func){
    return function curried(...args){
        if(args.length >= func.length){
            return func.apply(this, args);
        } else{
            return function(...args2){
                return curried.apply(this, arg.concat(args2));
            }
        }
    }
}


function sum(a, b, c){
    return a + b + c;
}

let curriedSum = curry(sum);

console.log(curriedSum(1, 2, 3));
console.log(curriedSum(1)(2, 3));
console.log(curriedSum(1)(2)(3));

```