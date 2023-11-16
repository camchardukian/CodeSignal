# Pages Numbering With Ink

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/labyrinth-of-nested-loops/pdw3izd7SpMTBJqSy)

**Prompt:** You work in a company that prints and publishes books. You are responsible for designing the page numbering mechanism in the printer. You know how many digits a printer can print with the leftover ink. Now you want to write a function to determine what the last page of the book is that you can number given the current page and numberOfDigits left. A page is considered numbered if it has the full number printed on it (e.g. if we are working with page 102 but have ink only for two digits then this page will not be considered numbered).

It's guaranteed that you can number the current page, and that you can't number the last one in the book.

**Initial Thoughts:**

```
// The simple way to solve this problem would be to loop for as long as numberOfDigits is greater than 0.

// With each iteration we'll convert current to a string, get the length, and subtract that from numberOfDigits. If numberOfDigits is greater than or equal to 0, we'll increment  current, and increment pages.
```

**My Solution:**

```
function solution(current, numberOfDigits) {
  while (numberOfDigits > 0) {
    numberOfDigits -= current.toString().length;
    if (numberOfDigits >= 0) {
      current++;
    }
  }
  return current - 1;
}
```

**Reflection:** The #3 or #4 top voted answer was more concise than mine:

```
const solution = (c, d) => {
  while ((d -= String(c++).length) >= 0);
  return c - 2;
};
```

However, I think it's preferable to write a few more lines of code if it makes our solution more readable, and I think in this case sacrificing a bit of brevity for more clarity was well worth it.
