44

# Is Sum of Consecutive 2

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/labyrinth-of-nested-loops/EQSjA5PRfyHueeNkj)

**Prompt:** Find the number of ways to express n as sum of some (at least two) consecutive positive integers.

**Initial Thoughts:**

```
// The naive solution here would be to have a base number, and then increment by base + 1, set base to base + 1, and repeat until our number is greater than or equal to n.

// If equal, we increment possibilities by 1. We then keep on repeating until base is equal to at least half of n.
```

**My Solution:**

```
function solution(n) {
  let counter;
  let possibilities = 0;
  for (let i = 1; i < n / 2; i++) {
    counter = i;
    for (let ii = i + 1; counter <= n; ii++) {
      counter += ii;
      if (counter === n) {
        possibilities += 1;
      }
    }
  }
  return possibilities;
}
```

**Reflection:** My solution seems to strike a good balance between conciseness, readability, and efficiency.
