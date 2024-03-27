## Valid Anagram
-Given two strings s and t, return true if t is an anagram of s, and false otherwise.
-An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.


```javascript
function isAnagram(s, t){
    const normalizeStr1 = s.replace(/[^\w]/g, '').toLowerCase();
    const normalizeStr2 = t.replace(/[^\w]/g, '').toLowerCase();

    // console.log(normalizeStr1, normalizeStr2);
    const frequency1 = {};
    const frequency2 = {};
    if(s.length !== t.length) return false;
    for(let elem of normalizeStr1){
        frequency1[elem] = (frequency1[elem] || 0) + 1;
    }
    for(let elem of normalizeStr2){
        frequency2[elem] = (frequency2[elem] || 0) + 1;
    }

    if(Object.keys(frequency1).length !== Object.keys(frequency2).length) return false;
    for(let x in frequency1){
        if( !x in frequency2 || (frequency1[x] !== frequency2[x])){
            return false;
        }
    }
    return true;
}
console.log(isAnagram("anagram", "nagaram"));
```
