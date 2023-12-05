# Solution

```java
public class Solution {
    public long subarraySum(int[] A) {

        long n = A.length;
        long ans = 0;

        for (int i = 0; i < n; i++) {
            ans += (long)A[i] * (i + 1) * (n - i);
        }

        return ans;

    }
}
```

## Time Complexity
- O(n)

## Space Complexity
- O(1)