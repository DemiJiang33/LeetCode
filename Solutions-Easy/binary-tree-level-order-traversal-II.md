## Binary Tree Level Order Traversal II

### Question

Given a binary tree, return the bottom-up level order traversal of its nodes' values. (ie, from left to right, level by level from leaf to root).

#### Example:
Given binary tree `[[3,9,20,null,null,15,7]`,
```shell
    3
   / \
  9  20
    /  \
   15   7
```

return its bottom-up level order traversal as:
```shell
[
  [15,7],
  [9,20],
  [3]
]
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
 * @param {TreeNode} root
 * @return {number[][]}
 */
var levelOrderBottom = function(root) {
    if(!root) return [];
    var output = [];
    dfs(root, 0, output)
    return output.reverse();
};

//Depth First Search
var dfs = function (node, level, output){
    if(!node) return 
    if(!output[level]) output[level] =[]
    output[level].push(node.val);
    
    // if(!output[level]){
    //     output[level] = [node.val]
    // }else{
    //     output[level].push(node.val);
    // }
    
    dfs(node.left, level+1, output);
    dfs(node.right, level+1, output);
}
```
