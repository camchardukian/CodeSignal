# Increase Number Roundness

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/loop-tunnel/KLbRMcWhaZi3dvYH5)

**Prompt:** Define an integer's roundness as the number of trailing zeroes in it.

Given an integer n, check if it's possible to increase n's roundness by swapping some pair of its digits.

**Initial Thoughts:**

```
// Our task is simple in that we just need to return true or false.

// If the first index of 0 is greater than -1, but less than the last index of a digit 1-9, we know to return true, otherwise return false.

// Given this, we should be able to use regex searches with indexOf and lastIndex of to get the answer.

// Update: We can't use regex with indexOf and lastIndexOf so we'll do a simple looping solution instead.
```

**My Solution:**

```
function solution(n) {
  const numberAsString = n.toString();
  let hasZero = false;
  for (let i = 0; i < numberAsString.length; i++) {
    if (numberAsString[i] == 0) {
      hasZero = true;
    }
    if (hasZero && numberAsString[i].match(/[1-9]/)) {
      return true;
    }
  }
  return false;
}
```

**Reflection:** My logic was decent as I analyzed this problem, but the solution I came up with was a bit overcomplicated.

All we needed to solve this problem was to recognize that as long as we had any number from 1-9 follow a 0, then we could return true.

Thus, it turns out the best solution for this problem actually was to use regex -- just not in the way I had originally intended:

```
function solution(n) {
  return /0[1-9]/.test(n);
}
```
