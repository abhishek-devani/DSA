# Solution

```java
public class Solution {
    public static int check(int[] A) {

        int n = A.length;
        HashMap<Integer, Integer> hashMap = new HashMap<>();

        for (int i = 0; i < n; i++) {
            if (hashMap.containsKey(A[i])) {
                int val = hashMap.get(A[i]);
                hashMap.put(A[i], val + 1);
            } else {
                hashMap.put(A[i], 1);
            }
        }

        for (int i = 0; i < n; i++) {
            if (hashMap.get(A[i]) == 1) {
                return A[i];
            }
        }
        return 0;

    }
}
```

### Time Complexity
- O(n)

### Space Complexity
- O(n)