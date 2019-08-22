## Remove Element

### Question

Given an array nums and a value val, remove all instances of that value in-place and return the new length.

Do not allocate extra space for another array, you must do this by **modifying the input array in-place** with O(1) extra memory.

The order of elements can be changed. It doesn't matter what you leave beyond the new length.

#### Example:
<pre>
Given nums = <b>[3,2,2,3]</b>, val = <b>3</b>,

Your function should return length = <b>2</b>, with the first two elements of nums being <b>2</b>.

It doesn't matter what you leave beyond the returned length.
</pre>

<pre>
Given nums = <b>[0,1,2,2,3,0,4,2]</b>, val = <b>2</b>,

Your function should return length = <b>5</b>, with the first five elements of nums containing <b>0</b>, <b>1</b>, <b>3</b>, <b>0</b>, and <b>4</b>.

Note that the order of those five elements can be arbitrary.

It doesn't matter what values are set beyond the returned length.
</pre>

#### Clarification:

Confused why the returned value is an integer but your answer is an array?

Note that the input array is passed in by **reference**, which means modification to the input array will be known to the caller as well.

Internally you can think of this:

```shell
// nums is passed in by reference. (i.e., without making a copy)
int len = removeElement(nums, val);

// any modification to nums in your function would be known by the caller.
// using the length returned by your function, it prints the first len elements.
for (int i = 0; i < len; i++) {
    print(nums[i]);
}
```

### Solution
```javascript
/**
 * @param {number[]} nums
 * @param {number} val
 * @return {number}
 */
var removeElement = function(nums, val) {
    for(var i=0; i<nums.length; i++){
        if(val == nums[i]){
            nums.splice(i,1);
            i--;
        }
    }
    console.log(nums);
};
```
