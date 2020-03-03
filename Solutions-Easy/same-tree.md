## Same Tree

### Question

Given two binary trees, write a function to check if they are the same or not.

Two binary trees are considered the same if they are structurally identical and the nodes have the same value.


#### Example:
```shell
Input:     1         1
          / \       / \
         2   3     2   3

        [1,2,3],   [1,2,3]

Output: true
```

```shell
Input:     1         1
          /           \
         2             2

        [1,2],     [1,null,2]

Output: false
```

```shell
Input:     1         1
          / \       / \
         2   1     1   2

        [1,2,1],   [1,1,2]

Output: false
```

### Solution
```javascript
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} p
 * @param {TreeNode} q
 * @return {boolean}
 */
var isSameTree = function(p, q) {
    if(!p && !q) return true // the same if both nodes are null
    if((!p && q) || (p && !q) || (p.val !== q.val)) return false 
    // not the same if either of the nodes is null or the values are different
    return isSameTree(p.left, q.left) && isSameTree(p.right, q.right);
};
```
