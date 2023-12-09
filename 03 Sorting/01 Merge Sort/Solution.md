# Solution

```java
public class Solution {
    public int[] solve(int[] A) {

        int n = A.length;
        int s = 0;
        int e = n - 1;
        return mergesort(A, s, e);

    }

    public int[] mergesort(int[] A, int s, int e) {

        if (s == e) {
            return A;
        }

        int mid = (s + e) / 2;
        mergesort(A, s, mid);
        mergesort(A, mid + 1, e);
        merge(A, s, mid, e);

        return A;

    }

    public void merge(int[] A, int s, int mid, int e) {

        int p1 = s;
        int p2 = mid + 1;
        int p3 = 0;

        int tmp[] = new int[e - s + 1];

        while (p1 <= mid && p2 <= e) {
            if (A[p1] < A[p2]) {
                tmp[p3] = A[p1];
                p1++;
            } else {
                tmp[p3] = A[p2];
                p2++;
            }
            p3++;
        }

        while (p1 <= mid) {
            tmp[p3] = A[p1];
            p1++;
            p3++;
        }

        while (p2 <= e) {
            tmp[p3] = A[p2];
            p2++;
            p3++;
        }

        int k = 0;
        for (int i = s; i <= e; i++) {
            A[i] = tmp[k];
            k++;
        }

    }

}
```

### Time Complexity
- O(nlogn)

### Space Complexity
- O(n)