# 02 Bubble Sort

## Problem Description

```markdown
Given a sorted array of integers `A` of size N and an integer B, 
where array A is rotated at some pivot unknown beforehand.

For example, the array [0, 1, 2, 4, 5, 6, 7] might become [4, 5, 6, 7, 0, 1, 2].

Your task is to search for the target value B in the array. If found, return its index; otherwise, return -1.

You can assume that no duplicates exist in the array.
```

**`Note:`** Users are expected to solve this in O(log(N)) time.

---
## Problem Constraints

```
1 <= |A| <= 100000
1 <= A[i] <= 10^9
```

---
## Input Format

```
The only argument given is the integer array A.
```

---
## Output Format

```
Return the single element that appears only once.
```

---
## Example Input

```markdown
Input 1:
> A = [1, 1, 7]

Input 2:
> A = [2, 3, 3]
```

---
## Example Output

```markdown
Output 1:
> 7

Output 2:
> 2
```

---
## Example Explanation

### Explanation 1

```markdown
7 appears once.
```

### Explanation 2

```markdown
2 appears once.
```