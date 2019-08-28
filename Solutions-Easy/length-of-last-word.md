## Length of Last Word

### Question

Given a string s consists of upper/lower-case alphabets and empty space characters `' '`, return the length of last word in the string.

If the last word does not exist, return 0.

#### Example:
```shell
Input: "Hello World"
Output: 5
```

#### Note:
A word is defined as a character sequence consists of non-space characters only.

### Solution
```javascript
/**
 * @param {string} s
 * @return {number}
 */
var lengthOfLastWord = function(s) {
    s = s.trim(); //Remove whitespace from both sides of a string
    if(s){
        var array = s.split(' ')
        var lastIndex = array.length-1;
        return array[lastIndex].length;
    }else{
        return 0;
    }
};
```
