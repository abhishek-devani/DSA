# Solution

```java
public class Solution {
    // DO NOT MODIFY THE ARGUMENTS WITH "final" PREFIX. IT IS READ ONLY
    public int trap(final int[] A) {

        int n = A.length;
        int water = 0;

        int prefixMax[] = new int[n];
        int suffixMax[] = new int[n];

        prefixMax[0] = A[0];
        suffixMax[n-1] = A[n-1];

        // Finding PrefixMax
        for (int i = 1; i < n; i++) {
            prefixMax[i] = Math.max(prefixMax[i-1], A[i]);
        }

        // Finding SuffixMax
        for (int i = n-2; i >= 0; i--) {
            suffixMax[i] = Math.max(suffixMax[i+1], A[i]);
        }

        // Calculating Water
        for(int i = 0; i < n; i++) {
            water += (Math.min(suffixMax[i], prefixMax[i]) - A[i]);
        }

        return water;

    }
}
```

### Time Complexity
- O(n)

### Space Complexity
- O(n)
