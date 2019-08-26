## Two Sum

### Question

Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

#### Example:
```shell
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
```

### Solution
```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    //var sums = []
    for(var i = 0 ; i< nums.length; i++){
        for(var j = i+ 1 ; j< nums.length ; j++){
    
            if(nums[i] + nums[j] == target){
                //sums.push(i, j)
                return [i,j];
            }
        }
    }
    //return sums;
};
```

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    var results = []
    var hashTable = {}
    for(var i = 0 ; i< nums.length; i++){
        var sumMinus = target - nums[i];
        if(hashTable[sumMinus] !== undefined){
            results.push(hashTable[sumMinus], i);
        }
        hashTable[nums[i]] = i;
    }
    //console.log(hashTable);
    return results;
};
```
