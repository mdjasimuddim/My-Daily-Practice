### Subarray Sum Equals K
- Given an array of integers nums and an integer k, return the total number of subarrays whose sum equals to k.
 - A subarray is a contiguous non-empty sequence of elements within an array.

```javascript

var subarraySum = function(nums, k) {
    const hashMap = {
        0:1,
    };
    let sum = 0;
    let result = 0;
    for(let i = 0; i < nums.length; i++){
        sum += nums[i];
        if([sum - k] in hashMap){
            result += hashMap[sum - k];
        }
        hashMap[sum] = (hashMap[sum]||0)+1;
    }
    return result;
};

console.log(subarraySum([1,2,3],2));
```
