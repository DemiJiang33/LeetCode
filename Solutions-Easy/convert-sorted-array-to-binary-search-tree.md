## Convert Sorted Array to Binary Search Tree

### Question

Given an array where elements are sorted in ascending order, convert it to a height balanced BST.

For this problem, a height-balanced binary tree is defined as a binary tree in which the depth of the two subtrees of every node never differ by more than 1.

#### Example:
```shell
 Given the sorted array: [-10,-3,0,5,9],

One possible answer is: [0,-3,9,-10,null,5], which represents the following height balanced BST:

      0
     / \
   -3   9
   /   /
 -10  5
```

### Solution
```javascript
/**
 * Definition for a binary tree node.
 * function TreeNode(val, left, right) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.left = (left===undefined ? null : left)
 *     this.right = (right===undefined ? null : right)
 * }
 */
/**
 * @param {number[]} nums
 * @return {TreeNode}
 */
var sortedArrayToBST = function(nums) {
    //base cases
    if(nums.length == 1) return new TreeNode(nums[0]);
    if(nums.length == 0) return null;
    
    //create a new TreeNode(center)
    var centerIndex = Math.floor(nums.length/2);
    var root = new TreeNode(nums[centerIndex]);
    
    //set left node to center of left subtree
    let leftSub = nums.slice(0, centerIndex);
    root.left = sortedArrayToBST(leftSub);
    
    //set right node to center of right subtree
    let rightSub = nums.slice(centerIndex+1, nums.length);
    root.right = sortedArrayToBST(rightSub);
    
    return root;
};
```
