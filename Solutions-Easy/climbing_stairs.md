## Climbing Stairs

### Question

You are climbing a stair case. It takes n steps to reach to the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

__Note:__ Given n will be a positive integer.

#### Example:
```shell
Input: 2
Output: 2
Explanation: There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps
```

```shell
Input: 3
Output: 3
Explanation: There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step
```

### Solution
```javascript
/**
 * @param {number} n
 * @return {number}
 */
//Loop Version (Iterative version)
var climbStairs = function(n) {
    var W = [0,1,2];
    for (var i=3; i<=n; i++){
        W[i] = W[i-1] + W[i-2]
    }
    return W[n];
};
```

```javascript
/**
 * @param {number} n
 * @return {number}
 */
//Memorized Recursive Version
var W = [0, 1, 2];
var climbStairs = function(n) {
    if (W[n] === undefined){
        W[n] = climbStairs(n - 2) + climbStairs(n - 1);
    }
    return W[n];
};
```
