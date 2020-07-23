## Climbing Stairs

### Question

You are climbing a stair case. It takes n steps to reach to the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

__Note:__ Given n will be a positive integer.

#### Example:
Given binary tree [3,9,20,null,null,15,7],
```shell
    3
   / \
  9  20
    /  \
   15   7
```
return its depth = 3.

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
 * @param {TreeNode} root
 * @return {number}
 */
var maxDepth = function(root) {
    if(!root) return 0;
    return 1+ Math.max(maxDepth(root.left), maxDepth(root.right));
};
```
