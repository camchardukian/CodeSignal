# Count Black Cells

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/loop-tunnel/RcK4vupi8sFhakjnh)

**Prompt:** Imagine a white rectangular grid of n rows and m columns divided into two parts by a diagonal line running from the upper left to the lower right corner. Now let's paint the grid in two colors according to the following rules:

A cell is painted black if it has at least one point in common with the diagonal;
Otherwise, a cell is painted white.
Count the number of cells painted black.

**Initial Thoughts:**

```
// The first time I tried to solve this problem I couldn't recognize a clear pattern so I looked at the solutions and saw I needed to find the greatest common divisor.

// Once I realized conceptually what needed to be done, I left the problem and returned 24 hours later to solve it on my own and this is what I got.
```

**My Solution:**

```
function getGCD(a, b) {
  if (!b) {
    return a;
  }
  return getGCD(b, a % b);
}

function solution(n, m) {
  return n + m + getGCD(n, m) - 2;
}
```

**Reflection:** See initial thoughts.
