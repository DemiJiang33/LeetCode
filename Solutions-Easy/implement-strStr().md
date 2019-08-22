## Implement strStr()

### Question

Implement __strStr()__.

Return the index of the first occurrence of needle in haystack, or **-1** if needle is not part of haystack.

#### Example:
<pre>
Input: haystack = "hello", needle = "ll"
Output: 2
</pre>

<pre>
Input: haystack = "aaaaa", needle = "bba"
Output: -1
</pre>

#### Clarification:

What should we return when <code>needle</code> is an empty string? This is a great question to ask during an interview.

For the purpose of this problem, we will return 0 when <code>needle</code> is an empty string. This is consistent to C's <code>strstr()</code> and Java's <code>indexOf()</code>.

### Solution
```javascript
/**
 * @param {string} haystack
 * @param {string} needle
 * @return {number}
 */
var strStr = function(haystack, needle) {
    var r = haystack.indexOf(needle);
    return r;
};
```
