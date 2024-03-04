## Memoization
Memoization is an optimization technique that makes applications more efficient and hence faster.

In fibonacci series, Normal code
```javascript
const fib = n => {
  if (n <= 1) return 1
  return fib(n - 1) + fib(n - 2)
}
```
Memoization code
```javascript
const fib = (n, memo) => {
    memo = memo || {}

    if (memo[n]) return memo[n]

    if (n <= 1) return 1
    return memo[n] = fib(n-1, memo) + fib(n-2, memo)
}
```


```javascript
function add(...x){
    return x.reduce((sum, curVal)=> sum + curVal);
}

const memo = (func) => {
    let cache = {};

    return function(...x){
        console.log(cache);
        const key = JSON.stringify(x);
        if(cache[key]){
            return cache[key];
        }else{
            const result = func(...x);
            cache[key] = result;
            return result;
        }
    }
}

const calculate = memo(add);
console.log(calculate(10, 20, 30, 40));
```