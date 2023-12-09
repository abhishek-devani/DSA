# Solution

```java
public class Solution {
    // DO NOT MODIFY THE ARGUMENTS WITH "final" PREFIX. IT IS READ ONLY
    public int search(final int[] A, int B) {

        int maxIndex = max(A);
        int n = A.length;

        // A[n-1] > A[0] ==> We are checking for sorted array with no rotation
        if (B >= A[n-1] || A[n-1] > A[0]) {
            return binarySearch(A, 0, maxIndex, B);
        } else {
            return binarySearch(A, maxIndex + 1, n-1, B);
        }

    }

    public int binarySearch(int[] A, int l, int r, int B) {

        int n = A.length;

        while (l <= r) {
            
            int mid = (l + r) / 2;

            if (A[mid] == B) {
                return mid;
            }
            if (A[mid] < B) {
                l = mid + 1;
            } else {
                r = mid - 1;
            }

        }
        return -1;

    }

    public int max(int[] A) {

        int n = A.length;
        int l = 0;
        int r = n - 1;

        if (A[0] > A[1]) {
            return 0;
        }

        if (A[n-1] > A[0]) {
            return n-1;
        }

        while (l <= r) {

            int mid = (l + r) / 2;

            if (A[mid] > A[mid-1] && A[mid] > A[mid+1]) {
                return mid;
            } else if (A[mid] > A[n-1]) {
                l = mid + 1;
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