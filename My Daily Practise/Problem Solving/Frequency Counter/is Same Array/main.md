## Is Array Same
- Write a function which accepts two arrays and check every value of the first array has it's corresponding in second array.
- The frequency value must be the same

```
isSame([1, 2, 4, 5], [3, 5, 6, 10])  // false
isSame([1, 2, 4, 5], [1, 4, 5, 2])  // true
isSame([1, 2, 4, 5], [3, 4, 5, 5, 2])  // false
isSame([1, 2, 4, 5], [3, 4, 2])  // false
```

`Time complexity O(n*m)`
```javascript
function isSame(arr1, arr2){
    if(arr1.length !== arr2.length) return false;

    for(let i = 0; i < arr1.length; i++){
        let index = arr2.indexOf(arr1[i]);

        if(index === -1){
            return false;
        } else{
            arr2.splice(index, 1)
        }
    }

    return true;
}

console.log(isSame([1, 2, 4, 5], [1, 4, 5, 2]))
```
`Time Complexity O(n) and space Complexity O(n+n) = O(n) `
```javascript
function isSame(arr1, arr2) 
{
    let hashTable1 = {};
    let hashTable2 = {};
    if(arr1.length !== arr2.length) return false;

    for(let x of arr1){
        hashTable1[x] = (hashTable1[x] || 0) + 1;
    }
    for(let x of arr2){
        hashTable2[x] = (hashTable2[x] || 0) + 1;
    }

    for(let elem in hashTable1){
        if(!elem in hashTable1 || hashTable1[elem] != hashTable2[elem]){
            return false;
        }
    }
    return true;

}
console.log(isSame([1, 2, 4, 5], [1, 4, 5, 2]))
```

