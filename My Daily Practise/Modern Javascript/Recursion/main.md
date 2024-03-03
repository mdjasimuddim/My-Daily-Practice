// 1 + 2 + 3 + 4 + 5 + .......
Recursion - call to function itself.

```javascript
function sum(n){
    if(n == 0){
        return 0;
    }else{
        return sum(n-1) + n;   // recursion
    }
}
console.log(sum(10));
// try to avoid for big value and it's very helpful for small value operation.

```