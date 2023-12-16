# Solution

```java
public class Solution {
    public int largestRectangleArea(int[] A) {

        int[] left = prevSmallerIdxLeft(A);
        int[] right = prevSmallerIdxRight(A);

        int n = A.length;
        int area = 0;

        for (int i = 0; i < n; i++) {
            int height = A[i];
            int l = left[i];
            int r = right[i];
            area = Math.max(area, (r-l-1)*height);
        }
        
        return area;

    }

    public int[] prevSmallerIdxLeft(int[] A) {

        int n = A.length;
        int[] ans = new int[n];
        Stack<Integer> stk = new Stack<>();

        for (int i = 0; i < n; i++) {
            ans[i] = -1;
        }

        for (int i = 0; i < n; i++) {

            while (stk.size() > 0 && A[stk.peek()] >= A[i]) {
                stk.pop();
            }

            if (stk.size() > 0) {
                ans[i] = stk.peek();
            }

            stk.push(i);

        }
        return ans;

    }

    public int[] prevSmallerIdxRight(int[] A) {

        int n = A.length;
        int[] ans = new int[n];
        Stack<Integer> stk = new Stack<>();

        for (int i = 0; i < n; i++) {
            ans[i] = -1;
        }

        for (int i = n-1; i >= 0; i--) {

            while (stk.size() > 0 && A[stk.peek()] >= A[i]) {
                stk.pop();
            }

            if (stk.isEmpty()) {
                ans[i] = n;
            } else {
                ans[i] = stk.peek();
            }

            stk.push(i);

        }
        return ans;

    }
}
```

### Time Complexity
- O(n)

### Space Complexity
- O(n)