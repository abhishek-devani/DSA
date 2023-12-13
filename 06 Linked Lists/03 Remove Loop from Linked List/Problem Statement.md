# 03 Remove Loop from Linked List

## Problem Description

```markdown
You are given a linked list that contains a loop.
You need to find the node, which creates a loop and break it by making the node point to NULL.
```

**`Note:`** If there are N nodes in the linked list and N is even then return the (N/2 + 1)th element.

---
## Problem Constraints

```
1 <= number of nodes <= 1000
```

---
## Input Format

```
The first of the input contains a LinkedList, where the first number is the number of nodes N, 
and the next N nodes are the node value of the linked list.
The second line of the input contains an integer which denotes the position of node where cycle starts.
```

---
## Output Format

```
Return the head of the updated linked list.
```

---
## Example Input

```markdown
Input 1:
> A = 1 -> 2
      ^    |
      | - - 

Input 2:
> A = 3 -> 2 -> 4 -> 5 -> 6
                ^         |
                |         |    
                - - - - - -
```

---
## Example Output

```markdown
Output 1:
> 1 -> 2 -> NULL

Output 2:
> 3 -> 2 -> 4 -> 5 -> 6 -> NULL
```

---
## Example Explanation

### Explanation 1

```markdown
Chain of 1->2 is broken.
```

### Explanation 2

```markdown
Chain of 4->6 is broken.
```