# Is Power?

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/labyrinth-of-nested-loops/yBFfNv5fTqhcacZ7w)

**Prompt:** Determine if the given number is a power of some non-negative integer.

**Initial Thoughts:**

```
// Can I just check to see if the square root of n is a non-floating point number? If so, I think that would confirm we should return true.

// But the problem with that I guess is it doesn't check to the power of 3, power of 4, etc.

// We could also check cube roots, roots of 4, roots of 5, and so on, but where would we stop?
```

**My Solution:**

```
function solution(n) {
  return Number.isInteger(Math.sqrt(n)) || Number.isInteger(Math.cbrt(n));
}
```

**Reflection:** My solution passed the test cases, but I think there are probably inputs like `243` that could break it.

It turns out the thing I was trying to avoid (nested loops), was actually the solution that made the most sense:

```
function solution(n) {
  if (n == 1) return true;
  for (i = 2; i <= Math.sqrt(n); i++) {
    for (j = 2; Math.pow(i, j) < n; j++);
    if (Math.pow(i, j) == n) return true;
  }
  return false;
}
```

This a great example of why if you can't see an optimal solution right away it's a good idea to produce a working naive solution.

The worst case scenario is you've demonstrated competence in that you can at least come to a working solution.

The best case scenario is that optimal solution you imagined isn't even possible and the "messy" way of doing things is actually the best way.
