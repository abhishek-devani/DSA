# Formulas

## Total Number Of Subarrays

```markdown
> n * (n + 1) / 2
```

## Particular Element in Total Number of Sub Arrays

```markdown
> **starting positions * ending positions**
> Ex. [9, 5, 4, 2, 3] find the total number of subarrays which contains 4.
> Starting position of 4 = [9, 5, 4] = 3
> Ending position for 4 = [4, 2, 3] = 3
> Ans = 3 * 3 = 9
```

### Final Formula

```markdown
> (i + 1) * (n - i)
> i is a index number of that element
> n is total number of elements in the array
```