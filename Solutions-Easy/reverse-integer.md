## Reverse Integer

### Question

Given a 32-bit signed integer, reverse digits of an integer.

#### Example:
```shell
Input: 123
Output: 321
```

```shell
Input: -123
Output: -321
```

```shell
Input: 120
Output: 21
```

#### Note:
Assume we are dealing with an environment which could only store integers within the 32-bit signed integer range: [−231,  231 − 1]. For the purpose of this problem, assume that your function returns 0 when the reversed integer overflows.

### Solution
```javascript
/**
 * @param {number} x
 * @return {number}
 */
var reverse = function(x) {
    var result = parseFloat(
        x
        .toString() //converts the given number into a String
        .split('') //converts the String into an Array of characters
        .reverse() //reverses the order of the items in the array
        .join('') //reassembles the reversed characters into a String
    ) * Math.sign(x)
    //multiplies the number with the sign of the original number provided  

    if (result < (Math.pow(-2,31)) || result > (Math.pow(2,31)-1)){
        result = 0;
    }

    return result;

};
```
