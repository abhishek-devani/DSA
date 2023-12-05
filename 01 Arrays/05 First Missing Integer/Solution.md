# Solutions

## Solution 1 (Brute Force)

```java
public class Solution {
    public int firstMissingPositive(int[] A) {

        int n = A.length;

        for (int i = 1; i <= n; i++) {
            if (search(A, i) == false) {
                return i;
            }
        }
        return n + 1;
    
    }

    public boolean search (int[] A, int i) {
        int n = A.length;
        for (int j = 0; j < n; j++) {
            if (A[j] == i) {
                return true;
            }
        }
        return false;
    }
}
```

### Time Complexity
- O(n^2)

### Space Complexity
- O(1)

---
## Solution 2 (Sorting)

```java
public class Solution {
    public int firstMissingPositive(int[] A) {

        Arrays.sort(A);

        int n = A.length;
        int ctr = 1;

        for (int i = 0; i < n; i++) {
            if (ctr == A[i]) {
                ctr++;
            }
        }
        return ctr;

    }
}
```

### Time Complexity
- O(nlogn)

### Space Complexity
- O(1)

---
## Solution 3 (Hashset)

```java
public class Solution {
    public int firstMissingPositive(int[] A) {

        int n = A.length;

        HashSet<Integer> hs = new HashSet<>();
        
        for (int i = 0; i < n; i++) {
            hs.add(A[i]);
        }

        for (int i = 1; i <= n; i++) {
            if (!hs.contains(i)) {
                return i;
            }
        }
        return n + 1;

    }
}
```

### Time Complexity
- O(n)

### Space Complexity
- O(n)

---
## Solution 4 (Keep the element at its right place)

```java
public class Solution {
    public int firstMissingPositive(int[] A) {

        int n = A.length;

        for (int i = 0; i < n; i++) {
            // Checking whether element is in proper range and not at the correct position
            while (A[i] > 0 && A[i] <= n && A[i] != i+1) {
                int val = A[i];
                // Checking if both the element are same or not
                if (A[i] == A[val-1]) {
                    break;
                }
                // swap the elements
                int tmp = A[i];
                A[i] = A[val-1];
                A[val-1] = tmp;
            }
        }

        for (int i = 0; i < n; i++) {
            if (A[i] != i+1) {
                return i+1;
            }
        }

        return n + 1;

    }

}
```

## Time Complexity
- O(n)

## Space Complexity
- O(1)