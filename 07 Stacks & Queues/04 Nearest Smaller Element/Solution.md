# Solutions

## Solution 1 (Brute Force)

```java
public class Solution {
    public int[] prevSmaller(int[] A) {

        int n = A.length;
        int ans[] = new int[n];

        for (int i = 0; i < n; i++) {
            ans[i] = -1;
        }

        for (int i = 0; i < n; i++) {
            for (int j = i - 1; j >= 0; j--) {
                if (A[j] < A[i]) {
                    ans[i] = A[j];
                    break;
                }
            }
        }
        return ans;

    }
}
```

### Time Complexity
- O(n^2^)

### Space Complexity
- O(1)

---
## Solution 2 (Optimized using stack)

```java
public class Solution {
    public int[] prevSmaller(int[] A) {

        int n = A.length;
        Stack<Integer> stack = new Stack<>();

        int ans[] = new int[n];
        stack.push(-1);

        for (int i = 0; i < n; i++) {

            while (A[i] <= stack.peek()) {
                stack.pop();
            }
            
            ans[i] = stack.peek();
            stack.push(A[i]);

        }
        return ans;

    }
}
```

### Time Complexity
- O(n)

### Space Complexity
- O(n)