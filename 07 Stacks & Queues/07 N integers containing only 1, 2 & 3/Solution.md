# Solution

```java
public class Solution {
    public int[] solve(int A) {

        int ans[] = new int[A];
        ArrayDeque<Integer> q = new ArrayDeque<>();

        q.add(1);
        q.add(2);
        q.add(3);

        for (int i = 0; i < A; i++) {
            int x = q.remove();
            ans[i] = x;
            q.add(x*10 + 1);
            q.add(x*10 + 2);
            q.add(x*10 + 3);
        }

        return ans;

    }
}
```

### Time Complexity
- O(A)

### Space Complexity
- O(n)