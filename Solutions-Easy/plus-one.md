## Plus One

### Question

Given a **non-empty** array of digits representing a non-negative integer, plus one to the integer.

The digits are stored such that the most significant digit is at the head of the list, and each element in the array contain a single digit.

You may assume the integer does not contain any leading zero, except the number 0 itself.

#### Example:
```shell
Input: [1,2,3]
Output: [1,2,4]
Explanation: The array represents the integer 123.
```

```shell
Input: [4,3,2,1]
Output: [4,3,2,2]
Explanation: The array represents the integer 4321.
```

### Solution
```javascript
/**
 * @param {number[]} digits
 * @return {number[]}
 */
var plusOne = function(digits) {
    var lastIndex = digits.length-1;
    var carry = 0;
    if(digits[lastIndex] < 9){
        digits[lastIndex] ++;
    }else{
        carry = 1;
        digits = carryFuc(digits, lastIndex, carry);
    }
    return digits;
};

function carryFuc(digits, currentIndex, carry){
    while(carry == 1 && currentIndex >=0){
        if(digits[currentIndex] < 9){
            digits[currentIndex] ++;
            carry = 0;
        }else{
            digits[currentIndex] = 0;
            currentIndex --;
        }
    }
    if(currentIndex < 0){
        digits.unshift(1);
    }
    return digits;
}
```
