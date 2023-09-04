# evenDigitsOnly

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-6/6cmcmszJQr6GQzRwW)

**Prompt:** Check if all digits of the given integer are even.

**Initial thoughts:**

```
// Here are two ways that popped into my head on how to solve this problem.

// 1. We parse the integer into a string, split it into an array, and loop through each index and check if the value at all indexes are even numbers (we can use the modulo operator to test).

// 2. The other approach would be to parse the integer into a string, and use a regex replace to replace any odd numbers with an arbitrary character such as a question mark or exclamation point. We could then check whether indexOf was greater than -1 because if so, we'd know there was at least 1 odd number inside the integer.
```

**Solution:**

```
function solution(n) {
  let nAsString = String(n);
  nAsString = nAsString.replace(/[13579]/, "!");
  return nAsString.indexOf("!") > -1 ? false : true;
}
```

**Reflection:** I'm happy to have come up with a concise solution that only took up a couple of lines of code.

I now realize, however, that I could make this solution even more concise by refactoring my code to use the `.match()` method rather than `.replace()`.
