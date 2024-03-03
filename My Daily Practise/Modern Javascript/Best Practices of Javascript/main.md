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
Give the variable name so that do not remain the purpose of Variable name
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

