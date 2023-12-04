# Solutions

## Solution 1 (BruteForce)

```java
public class Solution {
    // DO NOT MODIFY THE ARGUMENTS WITH "final" PREFIX. IT IS READ ONLY
    public int maxSubArray(final int[] A) {

        int n = A.length;
        int max = Integer.MIN_VALUE;

        for (int s = 0; s < n; s++) {
            for (int e = s; e < n; e++) {
                int sum = 0;
                for (int i = s; i <= e; i++) {
                    sum += A[i];
                }
                max = Math.max(max, sum);
            }
        }

        return max;

    }
}
```
### Time Complexity
- O(n^3)

### Space Complexity
- O(1)

---
## Solution 2 (Carry Forward)

```java
public class Solution {
    // DO NOT MODIFY THE ARGUMENTS WITH "final" PREFIX. IT IS READ ONLY
    public int maxSubArray(final int[] A) {

        int n = A.length;
        int max = Integer.MIN_VALUE;

        for (int s = 0; s < n; s++) {
            int sum = 0;
            for (int e = s; e < n; e++) {
                sum += A[e];
                max = Math.max(max, sum);
            }
        }

        return max;

    }
}
```

### Time Complexity
- O(n^2)

### Space Complexity
- O(1)

---
## Solution 3 (Kadane's Algorithm)

```java
public class Solution {
    // DO NOT MODIFY THE ARGUMENTS WITH "final" PREFIX. IT IS READ ONLY
    public int maxSubArray(final int[] A) {

        int n = A.length;
        int ans = Integer.MIN_VALUE;
        int sum = 0;

        for (int i = 0; i < n; i++) {
            sum += A[i];
            ans = Math.max(ans, sum);

            if (sum < 0) {
                sum = 0;
            }
        }

        return ans;

    }
}
```

## Time Complexity
- O(n)

## Space Complexity
- O(1)