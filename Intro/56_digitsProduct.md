# digitsProduct

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-12/NJJhENpgheFRQbPRA)

**Prompt:** Given an integer product, find the smallest positive (i.e. greater than 0) integer the product of whose digits is equal to product. If there is no such integer, return -1 instead.

**Initial Thoughts + Explanation (because I needed hints for this problem):**

```
// This problem brings me back to middle school math when we used to talk about things like least common multiple and greatest common factor.

// The first thing we need to do is tackle the unique cases of 0 returning 10 and 1 returning 1.

// Now, the way we're going to solve this problem is by attempting to divide the product by the largest 10 and under number possible.

// The reason we're doing this is because we want to find the largest divisor possible that has no remainder and stick that number in the ones column.

// Then we'll reset the divisor and try again to get the number in the tens column and so on until we get an answer, or until divisor equals one (which means no other divisor is possible and thus we need to return -1).
```

**My Solution:**

```
function solution(product) {
  if (product === 0) {
    return 10;
  } else if (product === 1) {
    return 1;
  }
  let divisor = 10;
  let columnMultiplier = 1;
  let answer = 0;
  while (product > 1) {
    if (--divisor === 1) {
      return -1;
    }
    while (product % divisor === 0) {
      product /= divisor;
      answer += divisor * columnMultiplier;
      columnMultiplier *= 10;
    }
  }
  return answer;
}
```

**Reflection:** This problem was tough. I was only able to get 14/18 test cases passing on my own an eventually I had to study different community submissions to better understand how to solve this problem.

With that being said, I think I'm now in a position where I'd be likely to be successful if I saw this problem again in the future.
