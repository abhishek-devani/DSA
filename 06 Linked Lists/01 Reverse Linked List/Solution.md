# Solution

```java
/**
 * Definition for singly-linked list.
 * class ListNode {
 *     public int val;
 *     public ListNode next;
 *     ListNode(int x) { val = x; next = null; }
 * }
 */
public class Solution {
    public ListNode reverseList(ListNode A) {

        ListNode tmp = null;
        ListNode res = null;

        ListNode curr = A;

        while (curr != null) {
            tmp = curr;
            curr = curr.next;
            tmp.next = res;
            res = tmp;
        }
        return res;

    }
}
```

### Time Complexity
- O(n)

### Space Complexity
- O(1)