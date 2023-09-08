# firstDigit

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-8/rRGGbTtwZe2mA8Wov)

**Prompt:** Find the leftmost digit that occurs in a given string.

**Initial Thoughts:**

```
// I'm pretty sure all we have to do to solve this problem is use regex match to identify the first index of [0-9].
```

**Solution:**

```
function solution(inputString) {
  return inputString.match(/[0-9]/).join("");
}
```

**Reflection:** My solution was very good, but not perfect. My initial thoughts were missing two key things.

One is that the match function returns an array, so we need to join that array to return a simple string.

The second, is that inside the regex we didn't need to write 0-9 because the escaped lowercase 'd' can be used for digits instead.
