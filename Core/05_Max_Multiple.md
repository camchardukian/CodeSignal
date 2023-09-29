# Max Multiple

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/intro-gates/HEsmEacHr2s9wahjr)

**Prompt:** Given a divisor and a bound, find the largest integer N such that:

N is divisible by divisor.
N is less than or equal to bound.
N is greater than 0.
It is guaranteed that such a number exists.

**Initial Thoughts:**

```
// This seems like it's another problem testing our knowledge of the modulo operator.

// Given that we're guaranteed such a number exists, all we need to do for this problem is find bound modulo operator divisor.

// If the result is 0, we return bound, otherwise we return bound minus the result.
```

**My Solution:**

```
function solution(divisor, bound) {
  return bound - (bound % divisor);
}
```

**Reflection:** This was a pretty straightforward problem. In a minute or two I came up with what looks to be the most concise and optimal solution possible.
