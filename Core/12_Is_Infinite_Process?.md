# Is Infinite Process?

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/at-the-crossroads/aFF9HDm2Rsti9j5kc)

**Prompt:** Given integers a and b, determine whether the following pseudocode results in an infinite loop

```
while a is not equal to b do
increase a by 1
decrease b by 1
```

Assume that the program is executed on a virtual machine which can store arbitrary long numbers and execute forever.

**Initial Thoughts:**

```
// If the function results in an infinite loop we return true.

// This means if a is larger than b, we should return true.

// If b is smaller than a, we need to check if the difference between b and a is divisible by two without a remainder.

// If so, we return false. If there is a remainder we return true.
```

**My Solution:**

```
function solution(a, b) {
  if (a > b) {
    return true;
  } else if ((b - a) % 2) {
    return true;
  }
  return false;
}
```

**Reflection:** Seems my pretty solution was pretty close to the ideal other than the fact that I could have made the code a bit more concise by getting rid of the `if` and `else if` like so:

```
function solution(a, b) {
  return a > b || (b - a) % 2 > 0;
}
```
