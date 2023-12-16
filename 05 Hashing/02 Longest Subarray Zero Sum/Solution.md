# Solutions

```markdown
Notes:
> Find the prefix sum.
> Subarray sum from i to j: ps[j] - ps[i-1]
> Here, Subarray sum is zero so, ps[j] - ps[i-1] = 0
> So, ps[j] = ps[i-1]
```

## Solution 1 (Brute Force)

```java
public class Solution {
    public int solve(int[] A) {

        int n = A.length;
        long ans = 0;
        for (int i = 0; i < n; i++) {
            long sum = 0;
            for (int j = i; j < n; j++) {
                sum += (long)A[j];
                if (sum == 0) {
                    ans = Math.max(ans, j-i+1);
                }
            }
        }
        return (int)ans;
    
    }
}
```

### Time Complexity
- O(n^2^)

### Space Complexity
- O(1)

---
## Solution 2

```java
public class Solution {
    public int solve(int[] A) {

        int n = A.length;
        long ps[] = new long[n];
        ps[0] = (long)A[0];

        for (int i = 1; i < n; i++) {
            ps[i] = (long)A[i] + ps[i-1];
        }

        HashMap<Long, Integer> hm = new HashMap<>();
        int ans = 0;

        for (int i = 0; i < n; i++) {
            if (hm.containsKey(ps[i])) {
                int v = hm.get(ps[i]);
                ans = Math.max(ans, i-v);
            } else {
                hm.put(ps[i], i);
            }
            if (ps[i] == 0) {
                ans = Math.max(ans, i+1);
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