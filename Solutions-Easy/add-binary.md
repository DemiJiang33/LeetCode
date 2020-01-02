## Add Binary

### Question

Given two binary strings, return their sum (also a binary string).

The input strings are both __non-empty__ and contains only characters `1` or `0`.

#### Example:
```shell
Input: a = "11", b = "1"
Output: "100"
```

```shell
Input: a = "1010", b = "1011"
Output: "10101"
```

### Solution
```javascript
/**
 * @param {string} a
 * @param {string} b
 * @return {string}
 */
var addBinary = function(a, b) {
    var i = a.length - 1;
    var j = b.length - 1;
    var carry = 0;
    var result = "";
    while(i >= 0 || j >= 0) {
        var m = i < 0 ? 0 : a[i] | 0;
        var n = j < 0 ? 0 : b[j] | 0;
        carry += m + n; // sum of two digits
        result = carry % 2 + result; // string concat
        carry = carry / 2 | 0; // remove decimals,  1 / 2 = 0.5, only get 0
        i--;
        j--;
    }
    if(carry !== 0) {
        result = carry + result;
    }
    return result;
};
```
