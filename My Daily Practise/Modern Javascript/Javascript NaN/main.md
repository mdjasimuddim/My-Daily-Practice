## NaN
```javascript
const result = "jasim" / 5;
console.log(result)   //NaN
```

`NaN - Not equal to itself`
```javascript
const weird = NaN;
console.log(weird === weird);  //false
```


```javascript
const result1 = "jasim" / 5;
const result2 = "Bad Programmer" / 3;

console.log(result1) // NaN
console.log(result2) // NaN

console.log(result1 === result2);  // false 
```


```javascript
const array = [NaN];
const result = array.includes(NaN);
console.log(result);  // true
```


## SumValueZero Algorithm
```javascript
const sameValueZero = (a, b) => {
    if(a===b || (Number.isNaN(a) && (Number.isNaN(a))){
        return true;
    }
    return false;
}
```
