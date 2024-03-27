### Group Anagrams
- Given an array of strings strs, group the anagrams together. You can return the answer in any order.
- An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.


```javascript
var groupAnagrams = function(strs) {
    const hashTable = {};
    for(let elem of strs){
        const sorted = elem.split('').sort().join('');
        if(hashTable[sorted]){
            hashTable[sorted].push(elem);
        }else{
            hashTable[sorted] = [elem];
        }
    }
    return Object.values(hashTable);
    // console.log(sorted);
};
console.log(groupAnagrams(["eat","tea","tan","ate","nat","bat"]));
```
