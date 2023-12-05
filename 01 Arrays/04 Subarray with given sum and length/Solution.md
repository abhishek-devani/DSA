# Solutions

## Solution 1 (Sliding Window)

```java
public class Solution {
    public int solve(int[] A, int B, int C) {

        int n = A.length;
        int sum = 0;

        // Sum of first B length of elements
        for (int i = 0; i < B; i++) {
            sum += A[i];
        }

        if (n == 1 && sum == C) {
            return 1;
        }

        int s = 1;
        int e = B;

        while (e < n) {
            sum = sum + A[e] - A[s-1];
            if (sum == C) {
                return 1;
            }
            s++;
            e++;
        }
        return 0;

    }
}
```
### Time Complexity
- O(n)

### Space Complexity
- O(1)

---
## Solution 2 (Prefix Sum)

```java
public class Solution {
    public int solve(int[] A, int B, int C) {

        int n = A.length;
        
        // Prefix Sum
        for (int i = 1; i < n; i++) {
            A[i] = A[i] + A[i-1];
        }

        if (A[B-1] == C) {
            return 1;
        }

        int s = 1;
        int e = B;

        while (e < n) {
            if (A[e] - A[s-1] == C) {
                return 1;
            }
            s++;
            e++;
        }

        return 0;

    }
}
```

### Time Complexity
- O(n)

### Space Complexity
- O(1)