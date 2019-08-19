## Valid Parentheses

### Question

Given a string containing just the characters `'('`, `')'`, `'{'`, `'}'`, `'['` and `']'`, determine if the input string is valid.

An input string is valid if:

Open brackets must be closed by the same type of brackets.
Open brackets must be closed in the correct order.
Note that an empty string is also considered valid.

#### Example:
```shell
Input: "()"
Output: true
```

```shell
Input: "()[]{}"
Output: true
```

```shell
Input: "(]"
Output: false
```

```shell
Input: "([)]"
Output: false
```

```shell
Input: "{[]}"
Output: true
```

### Solution
```javascript
/**
 * @param {string} s
 * @return {boolean}
 */
var isValid = function(s) {
    var a = [];
    if(s.length == 1){return false}
    for (var i=0; i<s.length ; i++){
        if (s[i] == '('){
            a.push(')');
        }else if(s[i] == '{'){
            a.push('}');
        }else if(s[i] == '['){
            a.push(']');
        }else{
            var pop = a.pop();
            if(pop !== s[i]){return false;}
        }
    }
    
    if (a.length !== 0) {return false};
    return true;
};
```

```javascript
var isValid = function(s) {
    var a = [];
    var map = {
        '(': ')',
        '{': '}',
        '[': ']'
    }
    if(s.length == 1){return false}
    for (var i=0; i<s.length ; i++){
        if (s[i] == '(' || s[i] == '{' || s[i] == '['){
            a.push(s[i]);
        }else{
            var pop = a.pop();
            if(s[i] !== map[pop]){return false;}
        }
    }
    if (a.length !== 0) {return false};
    return true;
};
```
