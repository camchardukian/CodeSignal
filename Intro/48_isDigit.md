# isDigit

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-11/Zr2XXEpkBPtYWqPJu)

**Prompt:** Determine if the given character is a digit or not.

**Initial Thoughts:**

```
// This seems like another simple problem that's trying to test my regex knowledge. It seems like we just need to test if the input 'symbol' is a digit or not.
```

**Solution:**

```
function solution(symbol) {
  return /\d/.test(symbol);
}
```

**Reflection:** My solution assumed that only a single character was going to be passed in, but other than that it was pretty much an ideal solution.

However, we also could've used the JS `isNaN` function to check whether the input was a number or not.
