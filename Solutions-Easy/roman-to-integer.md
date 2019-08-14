## Roman to Integer

### Question

Roman numerals are represented by seven different symbols: `I`, `V`, `X`, `L`, `C`, `D` and `M`.

```shell
Symbol       Value
I             1
V             5
X             10
L             50
C             100
D             500
M             1000
```

For example, two is written as `II` in Roman numeral, just two one's added together. Twelve is written as, `XII`, which is simply `X` + `II`. The number twenty seven is written as `XXVII`, which is `XX` + `V` + `II`.

Roman numerals are usually written largest to smallest from left to right. However, the numeral for four is not `IIII`. Instead, the number four is written as `IV`. Because the one is before the five we subtract it making four. The same principle applies to the number nine, which is written as IX. There are six instances where subtraction is used:

- `I` can be placed before `V` (5) and `X` (10) to make 4 and 9. 
- `X` can be placed before `L` (50) and `C` (100) to make 40 and 90. 
- `C` can be placed before `D` (500) and `M` (1000) to make 400 and 900.

Given a roman numeral, convert it to an integer. 
Input is guaranteed to be within the range from 1 to 3999.

#### Example:
```shell
Input: "III"
Output: 3
```

```shell
Input: "IV"
Output: 4
```

```shell
Input: "IX"
Output: 9
```

```shell
Input: "LVIII"
Output: 58
Explanation: L = 50, V= 5, III = 3.
```

```shell
Input: "MCMXCIV"
Output: 1994
Explanation: M = 1000, CM = 900, XC = 90 and IV = 4.
```

### Solution
```javascript
/**
 * @param {string} s
 * @return {number}
 */
var romanToInt = function(s) {
    var r = 0; // Initialize result 
    for (var i=0 ; i<s.length; i++){
        if(i+1 < s.length){
            var a = value(s[i]);
            var b = value(s[i+1]);
            if(a<b){
                r = r + b - a;
                i++;
            }else{
                r = r + a;
            }
        }else{
            r += value(s[i]);
        }
    }
    return r;
};


function value(v){
    if (v == 'I') 
        return 1; 
    if (v == 'V') 
        return 5; 
    if (v == 'X') 
        return 10; 
    if (v == 'L') 
        return 50; 
    if (v == 'C') 
        return 100; 
    if (v == 'D') 
        return 500; 
    if (v == 'M') 
        return 1000; 
}
```
