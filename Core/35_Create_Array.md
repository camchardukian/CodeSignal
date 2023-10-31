# Create Array

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/list-forest-edge/gmZFbpR9cirL3Jpf2)

**Prompt:** Given an integer size, return array of length size filled with 1s.

**Initial Thoughts:**

```
// I'm pretty sure there's an array.fill() method I can use. Otherwise, I could create a for loop and push repeatedly, or create a string "1" and use the string.repeat method, and then split the string into an array.
```

**My Solution:**

```
function solution(size) {
  return Array(size).fill(1);
}
```

**Reflection:** I'm happy to say that the solution I came up with ended up being the ideal solution -- on to the next problem.
