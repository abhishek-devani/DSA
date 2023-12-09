# Solutions

## Solution 1

```java
public class Solution {
    public int paint(int A, int B, int[] C) {

        long l = sumOfAllElements(C)[0];
        long r = sumOfAllElements(C)[1];

        long ans = Integer.MAX_VALUE;

        while (l <= r) {
            long mid = (l + r) / 2;
            if (check(mid, A, C)) {
                ans = mid;
                r = mid - 1;
            } else {
                l = mid + 1;
            }
        }

        return (int)((ans * B) % 10000003);

    }

    public boolean check(long mid, int painters, int[] tasks) {

        long n = tasks.length;
        long sum = 0;
        long noOfPainters = 1;

        for (int i = 0; i < n; i++) {
            sum += (tasks[i]);
            if (sum > mid) {
                noOfPainters++;
                sum = tasks[i];
                if (noOfPainters > painters) {
                    return false;
                }
            }
        }
        return true;

    }

    public long[] sumOfAllElements(int[] C) {

        int n = C.length;
        int sum = 0;
        int max = Integer.MIN_VALUE;

        for (int i = 0; i < n; i++) {
            max = Math.max(max, C[i]);
            sum += C[i];
        }
        return new long[] {max, sum};

    }
}
```

### Time Complexity
- O(n\*log(range)) ==> O(n*log(r-l))
- `r:` Sum of array
- `l:` Max element of array

### Space Complexity
- O(1)

---
## Solution 2

```java
public class Solution {
    public int paint(int A, int B, int[] C) {

        long l = sumOfAllElement(C, B)[0];
        long h = sumOfAllElement(C, B)[1];

        long ans = Integer.MAX_VALUE;

        while (l <= h) {
            long mid = (l + h) / 2;
            if (check(mid, A, B, C)) {
                ans = mid;
                h = mid - 1;
            } else {
                l = mid + 1;
            }
        }

        return (int)(ans % 10000003);

    }

    public boolean check(long mid, int painters, long time, int[] tasks) {

        int noOfPainters = 1;
        long sum = 0;

        for (int i = 0; i < tasks.length; i++) {
            sum += (tasks[i] * time);
            if (sum > mid) {
                noOfPainters++;
                sum = tasks[i] * time;
                if (noOfPainters > painters) {
                    return false;
                }
            }
        }
        return true;

    }

    public long[] sumOfAllElement(int[] A, int time) {

        int n = A.length;
        long sum = 0;
        long max = Integer.MIN_VALUE;
        
        for (int i = 0; i < n; i++) {
            max = Math.max(max, A[i]);
            sum += A[i];
        }
        return new long[] {max * time, sum * time};

    }
}
```

### Time Complexity
- O(n\*log(range)) ==> O(n*log(r-l))
- `r:` Sum of array
- `l:` Max element of array

### Space Complexity
- O(1)