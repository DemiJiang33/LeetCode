## Count and Say

### Question

The count-and-say sequence is the sequence of integers with the first five terms as following:
```shell
1.     1
2.     11
3.     21
4.     1211
5.     111221
```
`1` is read off as `"one 1"` or `11`.__
`11` is read off as `"two 1s"` or `21`.__
`21` is read off as `"one 2`, then `one 1"` or `1211`.__

Given an integer n where 1 ≤ n ≤ 30, generate the nth term of the count-and-say sequence. You can do so recursively, in other words from the previous member read off the digits, counting the number of digits in groups of the same digit.

Note: Each term of the sequence of integers will be represented as a string.

#### Example:
```shell
Input: 1
Output: "1"
Explanation: This is the base case.
```

```shell
Input: 4
Output: "1211"
Explanation: For n = 3 the term was "21" in which we have two groups "2" and "1", "2" can be read as "12" which means frequency = 1 and value = 2, the same way "1" is read as "11", so the answer is the concatenation of "12" and "11" which is "1211".
```

### Solution
```javascript
/**
 * @param {number} n
 * @return {string}
 */
var countAndSay = function(n) {
    var W = ['1','1','11','21','1211','111221'];
    for (var i = 6; i<=n; i++){
        var pre = W[i-1];
        var count = 1;
        var current = '';
        for(var j = 1; j<= pre.length-1; j++){
            if(pre[j] == pre[j-1]){
                count ++;
            }else{
                current += count;
                current += pre[j-1];
                count = 1;
            }
        }
        current += count;
        current += pre[pre.length-1];  
        W[i] = current;
    }
    return W[n]
};
```
