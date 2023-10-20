# Count Sum of Two Representations 2

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/loop-tunnel/hBw5BJiZ4LmXcy92u)

**Prompt:** Given integers n, l and r, find the number of ways to represent n as a sum of two integers A and B such that l ≤ A ≤ B ≤ r.

Example

For n = 6, l = 2, and r = 4, the output should be
solution(n, l, r) = 2.

There are just two ways to write 6 as A + B, where 2 ≤ A ≤ B ≤ 4: 6 = 2 + 4 and 6 = 3 + 3.

**Initial Thoughts:**

```
// It's taking me a little while to get my head around this problem.

// We need to get a bunch of numbers that add up to 'n'. Our addends must be greater than or equal to 'l' and less than or equal to 'r'.

// It seems like the brute force solution would be to subtract 'l' from 'n' and see if the result is greater than or equal to 'l' and less than or equal to 'r'.

// If so, we push to an array the equation as a string, and keep incrementing and trying again until we get to 'r'.

// Finally we create a set to get all of the unique values and return the size property of the set (which is similar to length) as the number of possibilities.
```

**My Solution:**

```
function solution(n, l, r) {
  const possibilities = [];
  for (let i = l; i <= r; i++) {
    const diff = n - i;
    if (diff >= l && diff <= r) {
      possibilities.push([i, diff].sort().toString());
    }
  }
  return new Set(possibilities).size;
}
```

**Reflection:** For time complexity, we're looking at O(r-l), which I think is good for this problem.
