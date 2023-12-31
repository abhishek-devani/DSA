# 01 Balanced Parenthesis

## Problem Description

```markdown
Given an expression string A, examine whether the pairs and the orders of
“{“,”}”, ”(“,”)”, ”[“,”]” are correct in A.

Refer to the examples for more clarity.
```

---
## Problem Constraints

```
1 <= |A| <= 100
```

---
## Input Format

```
The first and the only argument of input contains the string A having the parenthesis sequence.
```

---
## Output Format

```
Return 0 if the parenthesis sequence is not balanced.
Return 1 if the parenthesis sequence is balanced.
```

---
## Example Input

```markdown
Input 1:
> A = {([])}

Input 2:
> A = (){

Input 3:
> A = ()[]
```

---
## Example Output

```markdown
Output 1:
> 1

Output 2:
> 0

Output 3:
> 1
```

---
## Example Explanation

### Explanation 1

```markdown
You can clearly see that the first and third case contain valid parenthesis.
```

### Explanation 2

```markdown
In the second case, there is no closing bracket for {, thus the parenthesis sequence is invalid.
```