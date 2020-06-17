## Symmetric Tree

### Question

Given a binary tree, check whether it is a mirror of itself (ie, symmetric around its center).

#### Example:
For example, this binary tree `[1,2,2,3,4,4,3]` is symmetric:
```shell
    1
   / \
  2   2
 / \ / \
3  4 4  3
```

But the following `[1,2,2,null,3,null,3]` is not:
```shell
    1
   / \
  2   2
   \   \
   3    3
```

#### Follow up:
Follow up: Solve it both recursively and iteratively.

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
 * @return {boolean}
 */
var isSymmetric = function(root) {
    return isMirror(root, root);
};

//A tree is symmetric if the left subtree is a mirror reflection of the right subtree.
var isMirror = function(t1, t2){
    if(!t1 && !t2) return true // the same if both nodes are null
    if((!t1 && t2) || (t1 && !t2) || (t1.val !== t2.val)) return false 
    // not the same if either of the nodes is null or the values are different
    return isMirror(t1.left, t2.right) && isMirror(t1.right, t2.left);
}
```
