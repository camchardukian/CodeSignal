# Extra Number

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/at-the-crossroads/sgDWKCFQHHi5D3Szj)

**Prompt:** You're given three integers, a, b and c. It is guaranteed that two of these integers are equal to each other. What is the value of the third integer?

**Initial Thoughts:**

```
// Seems like we just need to check which two numbers are equal and return the value that isn't equal. We should be able to do this with just a few if statements.
```

**My Solution:**

```
function solution(a, b, c) {
  if (a === b) {
    return c;
  } else if (b === c) {
    return a;
  }
  return b;
}
```

**Reflection:** My solution was solid, but it could have been made a bit more concise by using ternary or bitwise operators.
