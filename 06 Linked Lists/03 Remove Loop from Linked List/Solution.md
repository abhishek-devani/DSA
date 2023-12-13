# Solution

## Steps

```markdown
1. Take two pointers slow and fast.
2. Slow moves one step and fast moves two steps.
3. Check if they meet somewhere or not.
4. If they meet then there is a loop.
5. take two slow pointes starting from A and previous slow pointer respectively.
6. move them until they meet.
7. Wherever they meet is the starting point of the cycle.
```

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
    public ListNode solve(ListNode A) {

        ListNode slow = A;
        ListNode fast = A;
        boolean isCycle = false;

        // Detect Cycle
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            if (slow == fast) {
                isCycle = true;
                break;
            }
        }

        if (isCycle == false) {
            return A;
        }

        // find the start of the Cycle
        ListNode slow1 = slow;
        ListNode slow2 = A;

        while (slow1 != slow2) {
            slow1 = slow1.next;
            slow2 = slow2.next;
        }

        // remove cycle
        ListNode ans = slow;

        while (ans.next != slow1) {
            ans = ans.next;
        }
        ans.next = null;
        
        return A;

    }
}
```

### Time Complexity
- O(n)

### Space Complexity
- O(1)