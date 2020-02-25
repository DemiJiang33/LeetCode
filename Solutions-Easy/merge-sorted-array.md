## Merge Sorted Array

### Question

Given two sorted integer arrays nums1 and nums2, merge nums2 into nums1 as one sorted array.

#### Note:
* The number of elements initialized in nums1 and nums2 are m and n respectively.
* You may assume that nums1 has enough space (size that is greater or equal to m + n) to hold additional elements from nums2.

#### Example:
```shell
Input: 
nums1 = [1,2,3,0,0,0], m = 3
nums2 = [2,5,6],       n = 3
Output: [1,2,2,3,5,6]
```

### Solution
```javascript
/**
 * @param {number[]} nums1
 * @param {number} m
 * @param {number[]} nums2
 * @param {number} n
 * @return {void} Do not return anything, modify nums1 in-place instead.
 */
var merge = function(nums1, m, nums2, n) {
    var lastIndex = m+n-1;
    m--;
    n--;
    while(n>=0){ //don't need to loop through the entire array. Just need to keep going until n >= 0.
        if(nums1[m]>=nums2[n]){
            nums1[lastIndex] = nums1[m]
            m--;
        }else{
            nums1[lastIndex] = nums2[n]
            n--;
        }
        lastIndex--;
    }
    return nums1;
};
```
