# Solution

```java

public class Solution {
    public int solve(int[] A) {

        for (int i = 1; i < A.length; i++) {
            A[i] = A[i-1] + A[i];
        }

        int n = A.length;

        if (A[0] == A[n-1]) {
            return 0;
        }

        for (int i = 1; i < n; i++) {
            if (A[i-1] == A[n-1] - A[i]) {
                return i;
            }
        }
        return -1;

    }
}


```