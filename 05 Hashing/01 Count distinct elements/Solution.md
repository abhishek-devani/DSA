# Solution

```java
public class Solution {
    public int solve(int[] A) {

        int n = A.length;
        HashSet<Integer> hs = new HashSet<>();

        for (int i = 0; i < n; i++) {
            hs.add(A[i]);
        }
        return hs.size();

    }
}
```

### Time Complexity
- O(n)

### Space Complexity
- O(n)
