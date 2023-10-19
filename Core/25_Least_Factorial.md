# Least Factorial

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/loop-tunnel/7BFPq6TpsNjzgcpXy)

**Prompt:** Given an integer n, find the minimal k such that

k = m! (where m! = 1 _ 2 _ ... \* m) for some integer m;
k >= n.
In other words, find the smallest factorial which is not less than n.

**Initial Thoughts:**

```
// Given that I see factorial mentioned in the prompt, I think this problem is a good candidate for recursion.

// We could also probably solve the problem with a simple loop.
```

**My Solution:**

```
function solution(n) {
  let value = 1;
  let currentMultiplier = 2;
  while (value < n) {
    value = value * currentMultiplier;
    currentMultiplier += 1;
  }
  return value;
}
```

**Reflection:** The other top community submissions were pretty similar to my solution.

Overall, I think we got a solid solution here, and I'm happy to finally be past the bitwise problems and get back to solving a wider variety of problems again.
