# Formulas

## Total Number Of Subarrays

```markdown
> n * (n + 1) / 2
```

## Particular Element in Total Number of Sub Arrays

```markdown
> starting positions * ending positions

> Ex. [9, 5, 4, 2, 3] find the total number of subarrays which contains 4.
> Starting position of 4 = [9, 5, 4] = 3
> Ending position for 4 = [4, 2, 3] = 3
> Ans = 3 * 3 = 9
```

### Final Formula

```markdown
> (i + 1) * (n - i)
> i represents index number of that element
> n represents total number of elements in the array
```

## Total numbers of subarrays of length K.

```markdown
> N - K + 1
> N represents total number of elements in the array
> K represents the length of subarray
```