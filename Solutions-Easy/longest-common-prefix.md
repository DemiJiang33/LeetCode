## Longest Common Prefix

### Question

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string `""`.

#### Example:
```shell
Input: ["flower","flow","flight"]
Output: "fl"
```

```shell
Input: ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.
```

#### Note:
All given inputs are in lowercase letters `a-z`.

### Solution
```javascript
/**
 * @param {string[]} strs
 * @return {string}
 */
var longestCommonPrefix = function(strs) {
    if (strs.length == 0) return "";
    var pre = strs[0];
    for (var i= 1; i < strs.length; i++){
        while(strs[i].indexOf(pre) !== 0){
            pre = pre.substring(0, pre.length-1);
            if(pre.length== 0){
                return '';
            }
        }
    }
    return pre;
};
```
