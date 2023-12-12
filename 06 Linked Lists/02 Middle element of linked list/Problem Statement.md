# 02 Middle element of linked list (Hare - Tortoise Algorithm)

## Problem Description

```markdown
Given a linked list of integers, find and return the middle element of the linked list.
```

**`Note:`** If there are N nodes in the linked list and N is even then return the (N/2 + 1)th element.

---
## Problem Constraints

```
1 <= length of the linked list <= 100000
1 <= Node value <= 10^9
```

---
## Input Format

```
The only argument given head pointer of linked list.
```

---
## Output Format

```
Return the middle element of the linked list.
```

---
## Example Input

```markdown
Input 1:
> A = 1 -> 2 -> 3 -> 4 -> 5

Input 2:
> A = 1 -> 5 -> 6 -> 2 -> 3 -> 4
```

---
## Example Output

```markdown
Output 1:
> 3

Output 2:
> 2
```

---
## Example Explanation

### Explanation 1

```markdown
The middle element is 3.
```

### Explanation 2

```markdown
The middle element in even length linked list of length N is ((N/2) + 1)th element which is 2.
```