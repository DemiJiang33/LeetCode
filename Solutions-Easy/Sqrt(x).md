## Sqrt(x)

### Question

Implement `int sqrt(int x)`.

Compute and return the square root of x, where x is guaranteed to be a non-negative integer.

Since the return type is an integer, the decimal digits are truncated and only the integer part of the result is returned.

#### Example:
```shell
Input: 4
Output: 2
```

```shell
Input: 8
Output: 2
Explanation: The square root of 8 is 2.82842..., and since 
             the decimal part is truncated, 2 is returned.
```

### Solution
```javascript
/**
 * @param {number} x
 * @return {number}
 */
var mySqrt = function(x) {
    var left = 1;
    var right = x;
    while(left <= right){
        var mid = Math.floor(left + (right - left) / 2);
        if (mid * mid > x){
            right = mid - 1;
        }else{
            left = mid + 1;
        }
    }
    return right;
};
```
