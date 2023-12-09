# Solution

```java
public class Solution {
    public int solve(int[] A) {

        int n = A.length;
        int l = 0;
        int r = n - 1;

        if (n == 1) {
            return A[0];
        }
        if (A[0] != A[1]) {
            return A[0];
        }
        if (A[n-1] != A[n-2]) {
            return A[n-1];
        }

        while (l <= r) {
            int mid = (l+r)/2;
            if(A[mid] != A[mid-1] && A[mid] != A[mid+1]) {
                return A[mid];
            }
            if (A[mid] == A[mid-1]) {
                mid = mid - 1;
            }
            if (mid % 2 == 0) {
                l = mid + 2;
            } else {
                r = mid - 1;
            }
        }
        return -1;
        
    }
}
```

### Time Complexity
- O(logn)

### Space Complexity
- O(1)