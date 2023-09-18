# sumUpNumbers

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-12/YqZwMJguZBY7Hz84T)

**Prompt:** CodeMaster has just returned from shopping. He scanned the check of the items he bought and gave the resulting string to Ratiorg to figure out the total number of purchased items. Since Ratiorg is a bot he is definitely going to automate it, so he needs a program that sums up all the numbers which appear in the given input.

Help Ratiorg by writing a function that returns the sum of numbers that appear in the given inputString.

**Initial Thoughts:**

```
// Hmmm... can we use regex matching to get an array of all the numbers and then use the reduce method to sum them up?

// I'm guessing this should work as we don't seem to need to account for numbers written out as words (e.g. ten, thirty, etc.)
```

**My Solution:**

```
function solution(inputString) {
  const numbers = inputString.match(/\d+/g);
  if (numbers) {
    return parseInt(numbers.reduce((a, b) => parseInt(a) + parseInt(b)));
  }
  return 0;
}
```

**Reflection:** My general logic was sound. There were some slightly more concise solutions submitted by the community such as this one:

```
function solution(inputString) {
  return (inputString.match(/\d+/g) || []).reduce((a, b) => a + +b, 0);
}
```

but overall my solution was satisfactory, even if it wasn't 100% optimized.

One cool thing I discovered while solving this problem is the [unary plus operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Unary_plus).
