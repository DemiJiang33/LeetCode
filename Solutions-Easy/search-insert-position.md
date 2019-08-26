## Search Insert Position

### Question

Given a sorted array and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.

You may assume no duplicates in the array.

#### Example:
<pre>
Input: [1,3,5,6], 5
Output: 2
</pre>

<pre>
Input: [1,3,5,6], 2
Output: 1
</pre>

<pre>
Input: [1,3,5,6], 7
Output: 4
</pre>

<pre>
Input: [1,3,5,6], 0
Output: 0
</pre>

### Solution
```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */
var searchInsert = function(nums, target) {
    if(nums.length == 0){return 0}
    if(target < nums[0]){return 0}
    if(target > nums[nums.length-1]){return nums.length}
    for(var i=0; i<nums.length; i++){
        if(target == nums[i]){
            return i;
        }
        if(target> nums[i] && target< nums[i+1]){
            return i+1;
        }
    }
};
```
