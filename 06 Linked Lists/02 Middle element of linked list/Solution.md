# Solutions

## Solution 1 (Using two loop)

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
    public int solve(ListNode A) {

        ListNode curr = A;
        int count = 0;

        while (curr != null) {
            curr = curr.next;
            count++;
        }

        curr = A;
        int mid = count/2 + 1;

        while (mid > 1) {
            curr = curr.next;
            mid--;
        }
        return curr.val;

    }
}
```

### Time Complexity
- O(n)

### Space Complexity
- O(1)

---
## Solution 2 (Using one loop)

### Steps

1. Slow moves once
2. Fast moves twice

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
    public int solve(ListNode A) {

        if (A == null) {
            return A.val;
        }

        ListNode fast = A;
        ListNode slow = A;

        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }
        return slow.val;

    }
}
```

### Time Complexity
- O(n)

### Space Complexity
- O(1)