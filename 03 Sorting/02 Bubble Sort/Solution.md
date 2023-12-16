# Solution

- Put the largest element at the last position by comparing two elements.

```java
public class Solution {
    public int[] bubbleSort(int[] A) {

        int n = A.length;
        for (int i = 0; i < n; i++) {
            // We can use 'j < n - i - 1' condition as well
            for (int j = 0; j < n - 1; j++) {
                if (A[j] > A[j+1]) {
                    int tmp = A[j];
                    A[j] = A[j+1];
                    A[j+1] = tmp;
                }
            }
        }
        return A;
        
    }
}
```

### Time Complexity
- O(n^2^)

### Space Complexity
- O(1)