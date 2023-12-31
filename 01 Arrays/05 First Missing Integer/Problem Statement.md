# 05 First Missing Integer

## Problem Description

```markdown
Given an unsorted integer array, A of size N. Find the first missing positive integer.
```
**`Note:`** Your algorithm should run in O(n) time and use constant space.

---
## Problem Constraints

```
1 <= N <= 1000000
-10^9 <= A[i] <= 10^9
```

---
## Input Format

```
First argument is an integer array A.
```

---
## Output Format

```
Return an integer denoting the first missing positive integer.
```

---
## Example Input

```markdown
Input 1:
> A = [1, 2, 0]

Input 2:
> A = [3, 4, -1, 1]

Input 3:
> A = [-8, -7, -6]
```

---
## Example Output

```markdown
Output 1:
> 3

Output 2:
> 2

Output 3:
> 1
```

---
## Example Explanation

### Explanation 1

```markdown
A = [1, 2, 0]
First positive integer missing from the array is 3.
```

### Explanation 2

```markdown
A = [3, 4, -1, 1]
First positive integer missing from the array is 2.
```

### Explanation 3

```markdown
A = [-8, -7, -6]
First positive integer missing from the array is 1.
```