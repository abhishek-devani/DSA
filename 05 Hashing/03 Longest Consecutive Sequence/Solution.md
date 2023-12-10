# Solution

```java
public class Solution {
    // DO NOT MODIFY THE ARGUMENTS WITH "final" PREFIX. IT IS READ ONLY
    public int longestConsecutive(final int[] A) {

        int n = A.length;
        int ans = 0;

        HashSet<Integer> hs = new HashSet<>();

        for (int i = 0; i < n; i++) {
            hs.add(A[i]);
        }

        for (Integer x : hs) {
            if (!hs.contains(x-1)) {
                int len = 0;
                int y = x;
                while (hs.contains(y)) {
                    len++;
                    y++;
                }
                ans = Math.max(ans, len);
            }
        }
        return ans;

    }
}
```

### Time Complexity
- O(n)

### Space Complexity
- O(n)