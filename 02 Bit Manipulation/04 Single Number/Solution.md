# Solution

```java
public class Solution {
    // DO NOT MODIFY THE ARGUMENTS WITH "final" PREFIX. IT IS READ ONLY
    public int singleNumber(final int[] A) {

        int res = 0;
        int n = A.length;

        for (int i = 0; i < n; i++) {
            res ^= A[i];
        }

        return res;

    }
}
```

### Time Complexity
- O(n)

### Space Complexity
- O(1)