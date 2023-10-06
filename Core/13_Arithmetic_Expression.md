# Arithmetic Expression

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/at-the-crossroads/QrCSNQWhnQoaK9KgK)

**Prompt:** Consider an arithmetic expression of the form a#b=c. Check whether it is possible to replace # with one of the four signs: +, -, \* or / to obtain a correct expression.

**Initial Thoughts:**

```
// For this question it seems like all we need to do is check if a operator b equals c.

// If we try all possible operators without a valid result we return false, otherwise if at any point we get a valid result then we return true.
```

**My Solution:**

```
function solution(a, b, c) {
  if (a + b === c || a - b === c || a * b === c || a / b === c) {
    return true;
  }
  return false;
}
```

**Reflection:** After looking at the community submissions, I can say that the solution I came up with is pretty much the optimal solution from both a performance and readability standpoint.
