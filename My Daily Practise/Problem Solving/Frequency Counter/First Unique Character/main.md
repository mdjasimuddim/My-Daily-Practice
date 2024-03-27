### First Unique Character in a String
- Given a string s, find the first non-repeating character in it and return its index. If it does not exist, return -1.

```javascript
var firstUniqChar = function(s) {
    const hashTable = {};
    for(let elem of s){
        hashTable[elem] = (hashTable[elem]||0)+1;
    }
    for(let i = 0; i < s.length; i++){
        if(hashTable[s[i]] === 1){
            return i;
        }
    }
    return -1;
    // console.log(hashTable);
};
console.log(firstUniqChar("loveleetcode"));
```
