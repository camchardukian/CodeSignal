# Rounders

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/loop-tunnel/H5PP5MXvYvWXxTytH)

**Prompt:** We want to turn the given integer into a number that has only one non-zero digit using a tail rounding approach. This means that at each step we take the last non 0 digit of the number and round it to 0 or to 10. If it's less than 5 we round it to 0 if it's larger than or equal to 5 we round it to 10 (rounding to 10 means increasing the next significant digit by 1). The process stops immediately once there is only one non-zero digit left.

**Initial Thoughts:**

```
// Here's the basic idea, we're going to loop through each value starting from the end of the number.

// We will round the result of the number divided by (1 + appropriate number of 0s).

// Then we keep doing this until we get to the ones column.
```

**My Solution:**

```
function solution(n) {
  const numberLength = n.toString().length;

  for (let i = numberLength - 1; i >= 0; i--) {
    n =
      Math.round(n / parseInt("1" + "0".repeat(numberLength - i - 1))) *
      parseInt("1" + "0".repeat(numberLength - i - 1));
  }
  return n;
}
```

**Reflection:** I think my solution was pretty efficient and similar logic wise to other top solutions.

In retrospect, I could have perhaps added clearer variable names to express my logic, but other than that I think we produced a solid solution.
