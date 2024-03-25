### Problem Name - Two Sum
- Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.
`Time complexity is O(n^2) `
```javascript
function twoSum(nums, target) {
    for(let i = 0; i < nums.length; i++){
        for(let j = 1; j < nums.length; j++){
            if(nums[i] + nums[j] === target){
                return [i, j];
            }
        }
    }
}
console.log(twoSum([3, 2, 4], 6))
```
`Time Complexity O(n)`
```javascript
function twoSum(nums, target) {
    const hashTable = {};
    for(let i = 0; i < nums.length; i++){
        const want = target - nums[i];
        if(want in hashTable){
            return [hashTable[want], i];
        }
        hashTable[nums[i]] = i
    }
}
console.log(twoSum([3, 2, 4], 6))
```

