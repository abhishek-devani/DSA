# Solution

```java
public class Solution {
    public int numSetBits(int A) {

        int ctr = 0;

        while (A != 0) {
            ctr += A & 1;
            A = A >> 1;
        }

        return ctr;

    }
}

```

### Time Complexity
- O(logn)

#### Reason
```
The reason for this time complexity is that the while loop iterates 
through each bit of the binary representation of the input integer A. 
In each iteration, the code performs a right shift operation (A = A >> 1), 
effectively dividing the value of A by 2. Since the loop continues until A becomes 0, 
the number of iterations is proportional to the number of bits in the binary representation of A, 
which is log N.
```

### Space Complexity
- O(1)