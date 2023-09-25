# Add Two Digits

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/intro-gates/wAGdN6FMPkx7WBq66)

**Prompt:** You are given a two-digit integer n. Return the sum of its digits.

**Initial Thoughts:**

```
// I'm pretty sure all I have to do is turn n into a string and then parseInt and add the first two indexes.
```

**My Solution:**

```
function solution(n) {
  const numberAsString = n.toString();
  return parseInt(numberAsString[0]) + parseInt(numberAsString[1]);
}
```

**Reflection:** My solution was valid and readable, but it was cool to see this other solution that was a bit more efficient though slightly less readable:

```
function solution(n) {
  return (n % 10) + Math.floor(n / 10);
}
```
