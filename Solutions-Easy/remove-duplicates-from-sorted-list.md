## Remove Duplicates from Sorted List

### Question

Given a sorted linked list, delete all duplicates such that each element appear only once.

#### Example:
```shell
Input: 1->1->2
Output: 1->2
```

```shell
Input: 1->1->2->3->3
Output: 1->2->3
```

### Solution
```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */
/**
 * @param {ListNode} head
 * @return {ListNode}
 */
var deleteDuplicates = function(head) {
    var current = head;
    while(current != null && current.next!= null){
        if ( current.next.val == current.val){
            current.next = current.next.next;
        }else{
            current = current.next;
        }
    }
    return head;
};
```
