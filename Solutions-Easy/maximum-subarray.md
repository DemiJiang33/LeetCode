## Maximum Subarray

### Question

Given an integer array `nums`, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

#### Example:
```shell
Input: [-2,1,-3,4,-1,2,1,-5,4],
Output: 6
Explanation: [4,-1,2,1] has the largest sum = 6.
```

#### Follow up:
If you have figured out the O(n) solution, try coding another solution using the divide and conquer approach, which is more subtle.

### Solution
```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var maxSubArray = function(nums) {
    var max = nums[0];
    for(var i=0; i<nums.length; i++){
        var sum = 0;
        for(j=i; j<nums.length; j++){
            sum += nums[j];
            max = Math.max(max, sum);
        }
    }
    return max;
};
```
