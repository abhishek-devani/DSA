# Solution

## Steps

```markdown
1. Sort the array
2. Find the maximum distance by subtracting first element from last element.
3. Find the minimum distance by finding min difference between two elements.
4. Check whether we can put the cows in given distance or not.
```

```java
public class Solution {
    public int solve(int[] A, int B) {

        Arrays.sort(A);

        int n = A.length;
        int l = minDist(A);
        int r = A[n-1] - A[0];
        int ans = -1;

        while (l <= r) {
            int mid = (l + r) / 2;
            if (check(mid, A, B)) {
                ans = mid;
                l = mid + 1;
            } else {
                r = mid - 1;
            }
        }
        return ans;

    }

    public boolean check(int mid, int[] stalls, int cows) {

        int n = stalls.length;
        int count = 1;
        int currentPlaced = stalls[0];

        for (int i = 0; i < n; i++) {
            if (stalls[i] - currentPlaced >= mid) {
                currentPlaced = stalls[i];
                count++;
                if (count == cows) {
                    return true;
                }
            }
        }
        return false;

    }

    public int minDist(int[] A) {
        
        int n = A.length;
        int min = Integer.MAX_VALUE;

        for (int i = 0; i < n-1; i++) {
            min = Math.min(min, A[i+1] - A[i]);
        }
        return min;
    }

}
```

### Time Complexity
- O(n\*logn + n*log(r-l)) ==> O(nlogn)

### Space Complexity
- O(1)
