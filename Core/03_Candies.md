# Candies

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/intro-gates/DdNKFA3XCX6XN7bNz)

**Prompt:** n children have got m pieces of candy. They want to eat as much candy as they can, but each child must eat exactly the same amount of candy as any other child. Determine how many pieces of candy will be eaten by all the children together. Individual pieces of candy cannot be split.

**Initial Thoughts:**

```
// This problem looks like a perfect use case for the modulo operator.

// We can do m candies % operator n children, and then our answer is the remainder subtracted from m candies.
```

**My Solution:**

```
function solution(n, m) {
  return m - (m % n);
}
```

**Reflection:** Again, this solution seems pretty optimal and matches the other most voted solutions on the platform.
